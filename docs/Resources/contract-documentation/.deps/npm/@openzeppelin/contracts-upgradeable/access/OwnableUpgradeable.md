## OwnableUpgradeable

\_Contract module which provides a basic access control mechanism, where
there is an account (an owner) that can be granted exclusive access to
specific functions.

By default, the owner account will be the one that deploys the contract. This
can later be changed with {transferOwnership}.

This module is used through inheritance. It will make available the modifier
`onlyOwner`, which can be applied to your functions to restrict their use to
the owner.\_

### OwnershipTransferred

```solidity
event OwnershipTransferred(address previousOwner, address newOwner)
```

### \_\_Ownable_init

```solidity
function __Ownable_init() internal
```

### \_\_Ownable_init_unchained

```solidity
function __Ownable_init_unchained() internal
```

### onlyOwner

```solidity
modifier onlyOwner()
```

### owner

```solidity
function owner() public view virtual returns (address)
```

_Returns the address of the current owner._

### \_checkOwner

```solidity
function _checkOwner() internal view virtual
```

### renounceOwnership

```solidity
function renounceOwnership() public virtual
```

\_Leaves the contract without owner. It will not be possible to call
`onlyOwner` functions anymore. Can only be called by the current owner.

NOTE: Renouncing ownership will leave the contract without an owner,
thereby removing any functionality that is only available to the owner.\_

### transferOwnership

```solidity
function transferOwnership(address newOwner) public virtual
```

_Transfers ownership of the contract to a new account (`newOwner`).
Can only be called by the current owner._

### \_transferOwnership

```solidity
function _transferOwnership(address newOwner) internal virtual
```
