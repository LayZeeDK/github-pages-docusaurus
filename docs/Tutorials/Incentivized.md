---
sidebar_position: 1
---

# Incentivized Testnet tasks

:::caution THERE IS NO PRESALE

MXC Token is already listed on Coinbase, Kraken, Crypto.com and Binance.us, there is no Presale or Public sale.

:::

The purpose of the Wannsee testnet is to bring the largest Web3 IoT network that MXC community built in 177 countries to MXC zkEVM and Arbitrum ecosystem.

## Token properties:

|                            |                                          |
|----------------------------|------------------------------------------|
| Initial supply cap         | 2.6 billion                              |
| Launched date              | 2018 August                              |
| Inflation/Deflation rate   | Same as Ethereum as the gas is MXC Token |
| Minting/burning mechanism  | L2 Smart Contract                        |
| Bridgeable to Ethereum L1? | Yes                                      |
| Tokens launch on           | MXC zkEVM                                |
| Airdrop snapshot           | TBD                                      |
| Claiming started           | After Announcement                       |
| Claiming ends              | After Announcement                       |


## Token allocation & airdrop distribution:

| Percentage of initial supply | Number of tokens | Allocated to                                                  |
|------------------------------|------------------|---------------------------------------------------------------|
| 40%                          | 1,065,986,320       | MXC DAO treasury                |
| 30%                          | 799,489,740        | MXC DataDash App Users                                        |
| 20%                          | 532,993,160        | Free unlocked circulation from 2019                           |
| 10%                          | 266,496,580        | Users of the MXC zkEVM (via airdrop to user wallet addresses) |


Up to 10% of the circulation will participate in the airdrop, when the MXC token price listed on Coinbase Pro reaches a certain threshold at the announced block height, it will open the more percentages like the following table shows:

| Participation wallets | Total Percentage of MXC token |
|-----------------------|-------------------------------|
| Under $0.2            | 2%                           |
| $0.2-0.5              | 4%                           |
| $0.5-0.8              | 6%                           |
| $0.8-1                | 8%                           |
| Above $1              | 10%                          |



### User airdrop eligibility details

A points system was used to determine the number of tokens that airdrop recipients can claim. Points criteria was focused primarily on MXC zkEVM; however, there was a small subset of criteria applied to activity on DataHighway.com. Points earned on DataHighway.com could either bring a user up to 4 points total, or give them one additional point if they had already scored 4 points or more on MXC zkEVM. You earn maximum one point per qualifying action performed before the snapshot date. Point scores were capped at 30.

Additionally, as the criteria and design of the airdrop as a whole was intentioned to reward early adopters, points scored (minimum of three) before announcement link (later available) are worth twice as much as points scored after.

**Qualifying actions:**

Points earned on MXC zkEVM

 1. Create Initial Sensor Offerings (Name of the token created should contain an IoT sensor)
2. Create IoT NFTs (Name of the NFT created should be a real-world object)
3. Run MXC zkEVM Supernodes
4. Creating a MXC zkEVM wallet
 5. Conducted more than four transactions or interacted with more than four different smart contracts
 6. Conducted more than ten transactions or interacted with more than ten different smart contracts
 7. Conducted more than 25 transactions or interacted with more than 25 different smart contracts
 8. Conducted more than 100 transactions or interacted with more than 100 different smart contracts
 9. Conducted Sensor Tokens/IoT NFTs transactions exceeding in the aggregate $10,000 in value
 10. Conducted Sensor Tokens/IoT NFTs transactions exceeding in the aggregate $50,000 in value
 11. Conducted Sensor Tokens/IoT NFTs transactions exceeding in the aggregate $250,000 in value
 12. Minting Hexagon map NFT
 13. Creating MXC name service domain
 14. **Claim the [MOON token](https://contract_addr) and send to the referrer person, no upper limit**



Points earned on DataHighway.com 

 1. Creating assets on DataHighway.com 
 2. Conducted more than three transactions
 3. Conducted more than five transactions
 4. Conducted more than ten transactions

<br />

**Converting Points to tokens:**

<table className="small-table">
    <tr>
        <td><strong>Points scored (values represent points scored pre-MXC zkEVM)</strong></td>
        <td><strong>Airdrop entitlement</strong></td>
    </tr>
    <tr>
        <td>Less than 3</td>
        <td>Not eligible</td>
    </tr>
    <tr>
        <td>3</td>
        <td>1,250</td>
    </tr>
    <tr>
        <td>4</td>
        <td>1,750</td>
    </tr>
    <tr>
        <td>5</td>
        <td>2,250</td>
    </tr>
    <tr>
        <td>6</td>
        <td>3,250</td>
    </tr>
    <tr>
        <td>7</td>
        <td>3,750</td>
    </tr>
    <tr>
        <td>8</td>
        <td>4,250</td>
    </tr>
    <tr>
        <td>9</td>
        <td>6,250</td>
    </tr>
    <tr>
        <td>10</td>
        <td>6,750</td>
    </tr>
    <tr>
        <td>11</td>
        <td>7,250</td>
    </tr>
    <tr>
        <td>12 - 18</td>
        <td>10,250</td>
    </tr>
    <tr>
        <td>18 - 25</td>
        <td>20,000</td>
    </tr>
    <tr>
        <td>25 - 30</td>
        <td>40,000</td>
    </tr>
</table>

<br />

As described earlier, points scored before and after announcement were weighted differently. Points scored before announcement were worth twice as much as points scored after -- as a result any points scored after announcement resulted in half as much of an allocation per point shown in the table above. If an address only became fully eligible (minimum of three points) post-announcement, all points scored counted as post-announcement points. Thus, the minimum airdrop entitlement is 625 tokens, half of the minimum entitlement in the table above; the maximum airdrop entitlement is 40000 tokens.

**User protections:**

To prevent bots from taking advantage of the airdrop, a number of anti-Sybil rules were established:

 - If an airdrop recipient's wallet transactions have all occurred within a 48-hour period, **one point is subtracted**.
 - If an airdrop recipient's wallet balance is less than 500 MXC, **and** if the wallet hasn't interacted with more than one smart contract, **one point is subtracted**.
 - If an airdrop recipient's wallet address has been identified as a Sybil address during the Hop protocol bounty program **the recipient is disqualified**. 

Refer to [Sybil Hunting](https://github.com/mxczkevm/sybil-detection) to learn more about the Sybil mitigation methodology. Refer to our [Sybil accounts](https://github.com/mxczkevm/sybil-detection) concept document for a conceptual introduction to Sybil accounts.

### DAO airdrop criteria and distribution

A separate distribution was allocated for DAOs that are building applications in the MXC ecosystem, as well as the Protocol Guild, a collective of Ethereum contributors. In putting together this criteria we worked with Nansen and analyzed on-chain data to determine how many tokens each DAO community was granted. In doing so we took into account a variety of qualitative and quantitative metrics including when the protocol launched, whether it was native or multichain, how much TVL, activity, transaction volume, value of transactions it had, as well as the consistency of maintaining those metrics. The goal of using a broad variety of criteria was recognizing that MXC is home to a diversity of projects that have different KPIs and user interactions.



### Vesting and lockup details

While the user and DAO airdrops will be available in one week, all investor and team tokens are subject to 4 year lockups, with the first unlocks happening in one year and then monthly unlocks for the remaining three years.



