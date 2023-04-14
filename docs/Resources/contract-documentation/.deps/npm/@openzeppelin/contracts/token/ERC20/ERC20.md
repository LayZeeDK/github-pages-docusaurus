## ERC20

\_Implementation of the {IERC20} interface.

This implementation is agnostic to the way tokens are created. This means
that a supply mechanism has to be added in a derived contract using {\_mint}.
For a generic mechanism see {ERC20PresetMinterPauser}.

TIP: For a detailed writeup see our guide
https://forum.openzeppelin.com/t/how-to-implement-erc20-supply-mechanisms/226[How
to implement supply mechanisms].

We have followed general OpenZeppelin Contracts guidelines: functions revert
instead returning `false` on failure. This behavior is nonetheless
conventional and does not conflict with the expectations of ERC20
applications.

Additionally, an {Approval} event is emitted on calls to {transferFrom}.
This allows applications to reconstruct the allowance for all accounts just
by listening to said events. Other implementations of the EIP may not emit
these events, as it isn't required by the specification.

Finally, the non-standard {decreaseAllowance} and {increaseAllowance}
functions have been added to mitigate the well-known issues around setting
allowances. See {IERC20-approve}.\_

### constructor

```solidity
constructor(string name_, string symbol_) public
```

\_Sets the values for {name} and {symbol}.

The default value of {decimals} is 18. To select a different value for
{decimals} you should overload it.

All two of these values are immutable: they can only be set once during
construction.\_

### name

```solidity
function name() public view virtual returns (string)
```

_Returns the name of the token._

### symbol

```solidity
function symbol() public view virtual returns (string)
```

_Returns the symbol of the token, usually a shorter version of the
name._

### decimals

```solidity
function decimals() public view virtual returns (uint8)
```

\_Returns the number of decimals used to get its user representation.
For example, if `decimals` equals `2`, a balance of `505` tokens should
be displayed to a user as `5.05` (`505 / 10 ** 2`).

Tokens usually opt for a value of 18, imitating the relationship between
Ether and Wei. This is the value {ERC20} uses, unless this function is
overridden;

NOTE: This information is only used for _display_ purposes: it in
no way affects any of the arithmetic of the contract, including
{IERC20-balanceOf} and {IERC20-transfer}.\_

### totalSupply

```solidity
function totalSupply() public view virtual returns (uint256)
```

_See {IERC20-totalSupply}._

### balanceOf

```solidity
function balanceOf(address account) public view virtual returns (uint256)
```

_See {IERC20-balanceOf}._

### transfer

```solidity
function transfer(address to, uint256 amount) public virtual returns (bool)
```

\_See {IERC20-transfer}.

Requirements:

- `to` cannot be the zero address.
- the caller must have a balance of at least `amount`.\_

### allowance

```solidity
function allowance(address owner, address spender) public view virtual returns (uint256)
```

_See {IERC20-allowance}._

### approve

```solidity
function approve(address spender, uint256 amount) public virtual returns (bool)
```

\_See {IERC20-approve}.

NOTE: If `amount` is the maximum `uint256`, the allowance is not updated on
`transferFrom`. This is semantically equivalent to an infinite approval.

Requirements:

- `spender` cannot be the zero address.\_

### transferFrom

```solidity
function transferFrom(address from, address to, uint256 amount) public virtual returns (bool)
```

\_See {IERC20-transferFrom}.

Emits an {Approval} event indicating the updated allowance. This is not
required by the EIP. See the note at the beginning of {ERC20}.

NOTE: Does not update the allowance if the current allowance
is the maximum `uint256`.

Requirements:

- `from` and `to` cannot be the zero address.
- `from` must have a balance of at least `amount`.
- the caller must have allowance for `from`'s tokens of at least
  `amount`.\_

### increaseAllowance

```solidity
function increaseAllowance(address spender, uint256 addedValue) public virtual returns (bool)
```

\_Atomically increases the allowance granted to `spender` by the caller.

This is an alternative to {approve} that can be used as a mitigation for
problems described in {IERC20-approve}.

Emits an {Approval} event indicating the updated allowance.

Requirements:

- `spender` cannot be the zero address.\_

### decreaseAllowance

```solidity
function decreaseAllowance(address spender, uint256 subtractedValue) public virtual returns (bool)
```

\_Atomically decreases the allowance granted to `spender` by the caller.

This is an alternative to {approve} that can be used as a mitigation for
problems described in {IERC20-approve}.

Emits an {Approval} event indicating the updated allowance.

Requirements:

- `spender` cannot be the zero address.
- `spender` must have allowance for the caller of at least
  `subtractedValue`.\_

### \_transfer

```solidity
function _transfer(address from, address to, uint256 amount) internal virtual
```

### \_mint

```solidity
function _mint(address account, uint256 amount) internal virtual
```

### \_burn

```solidity
function _burn(address account, uint256 amount) internal virtual
```

### \_approve

```solidity
function _approve(address owner, address spender, uint256 amount) internal virtual
```

### \_spendAllowance

```solidity
function _spendAllowance(address owner, address spender, uint256 amount) internal virtual
```

### \_beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address from, address to, uint256 amount) internal virtual
```

### \_afterTokenTransfer

```solidity
function _afterTokenTransfer(address from, address to, uint256 amount) internal virtual
```
