## SafeERC20Upgradeable

_Wrappers around ERC20 operations that throw on failure (when the token
contract returns false). Tokens that return no value (and instead revert or
throw on failure) are also supported, non-reverting calls are assumed to be
successful.
To use this library you can add a `using SafeERC20 for IERC20;` statement to your contract,
which allows you to call the safe operations as `token.safeTransfer(...)`, etc._

### safeTransfer

```solidity
function safeTransfer(contract IERC20Upgradeable token, address to, uint256 value) internal
```

### safeTransferFrom

```solidity
function safeTransferFrom(contract IERC20Upgradeable token, address from, address to, uint256 value) internal
```

### safeApprove

```solidity
function safeApprove(contract IERC20Upgradeable token, address spender, uint256 value) internal
```

### safeIncreaseAllowance

```solidity
function safeIncreaseAllowance(contract IERC20Upgradeable token, address spender, uint256 value) internal
```

### safeDecreaseAllowance

```solidity
function safeDecreaseAllowance(contract IERC20Upgradeable token, address spender, uint256 value) internal
```

### safePermit

```solidity
function safePermit(contract IERC20PermitUpgradeable token, address owner, address spender, uint256 value, uint256 deadline, uint8 v, bytes32 r, bytes32 s) internal
```
