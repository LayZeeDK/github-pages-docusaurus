## Create2Upgradeable

\_Helper to make usage of the `CREATE2` EVM opcode easier and safer.
`CREATE2` can be used to compute in advance the address where a smart
contract will be deployed, which allows for interesting new mechanisms known
as 'counterfactual interactions'.

See the https://eips.ethereum.org/EIPS/eip-1014#motivation[EIP] for more
information.\_

### deploy

```solidity
function deploy(uint256 amount, bytes32 salt, bytes bytecode) internal returns (address addr)
```

### computeAddress

```solidity
function computeAddress(bytes32 salt, bytes32 bytecodeHash) internal view returns (address)
```

### computeAddress

```solidity
function computeAddress(bytes32 salt, bytes32 bytecodeHash, address deployer) internal pure returns (address addr)
```
