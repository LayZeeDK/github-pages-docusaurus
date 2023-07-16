# Deploy Docusaurus website to GitHub Pages using GitHub Actions

This repository is an example of deploying a Docusaurus website to GitHub Pages using GitHub Actions.

## Configuring the GitHub repository

It uses the _new_ GitHub Pages experience with GitHub Actions to deploy the website.

Enable this experience in _GitHub.com -> Repository -> Settings -> Pages -> Build and deployment -> Source_ by selecting _GitHub Actions_ instead of the legacy _Deploy from a branch_ option.

In _GitHub.com -> Repository -> Settings -> Environments_ you should see a GitHub Environment named `github-pages`.

## Configuring Docusaurus

Generate a Docusuarus website using the following command:

```shell
yarn create docusaurus <folder-name> classic --typescript
```

Make the following changes to the `docusaurus.config.js` configuration file:

1. Create the constants `organizationName` and `projectName`
   ```javascript
   const organizationName = "<github-organization-name>";
   const projectName = "<repository-name>";
   ```
1. Set the URL
   ```javascript
   const config = {
     // (...)
     url: `https://${organizationName}.github.io`,
   };
   const baseUrl = /${projectName}/`;
   ```
1. Configure the base URL
   ```javascript
   const config = {
     // (...)
     baseUrl: `/${projectName}/`,
   };
   ```
1. Set the `organizationName` and `projectName` options

   ```javascript
   const organizationName = "<github-organization-name>";
   const projectName = "<repository-name>";

   const config = {
     // (...)
     organizationName,
     projectName,
   };
   ```

1. Configure the blog and docs edit URLs
   ```javascript
   const config = {
     // (...)
     presets: [
       [
         "classic",
         /** @type {import('@docusaurus/preset-classic').Options} */
         ({
           // (...)
           docs: {
             // (...)
             editUrl: `https://github.com/${organizationName}/${projectName}/tree/main/`,
           },
           blog: {
             // (...)
             editUrl: `https://github.com/${organizationName}/${projectName}/tree/main/`,
           },
         }),
       ],
     ],
   };
   ```

## Adding a GitHub Actions deployment workflow

Use a GitHub Actions workflow template for GitHub Pages from the [`actions/starter-workflows`](https://github.com/actions/starter-workflows) repository. Place it in `.github/workflows/<workflow-name>.yml`.

Add steps for building the website before the GitHub Pages actions are executed and specify the `path` to the `actions/upload-pages-artifact`:

```yaml
# (...)
jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      # 👇 Build steps
      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 16.x
          cache: yarn
      - name: Install dependencies
        run: yarn install --frozen-lockfile --non-interactive
      - name: Build
        run: yarn build
      # 👆 Build steps
      - name: Setup Pages
        uses: actions/configure-pages@v3
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v2
        with:
          # 👇 Specify build output path
          path: build
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v2
```
