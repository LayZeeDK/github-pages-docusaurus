## ECDSA

\_Elliptic Curve Digital Signature Algorithm (ECDSA) operations.

These functions can be used to verify that a message was signed by the holder
of the private keys of a given address.\_

### RecoverError

```solidity
enum RecoverError {
  NoError,
  InvalidSignature,
  InvalidSignatureLength,
  InvalidSignatureS,
  InvalidSignatureV
}
```

### tryRecover

```solidity
function tryRecover(bytes32 hash, bytes signature) internal pure returns (address, enum ECDSA.RecoverError)
```

### recover

```solidity
function recover(bytes32 hash, bytes signature) internal pure returns (address)
```

### tryRecover

```solidity
function tryRecover(bytes32 hash, bytes32 r, bytes32 vs) internal pure returns (address, enum ECDSA.RecoverError)
```

### recover

```solidity
function recover(bytes32 hash, bytes32 r, bytes32 vs) internal pure returns (address)
```

### tryRecover

```solidity
function tryRecover(bytes32 hash, uint8 v, bytes32 r, bytes32 s) internal pure returns (address, enum ECDSA.RecoverError)
```

### recover

```solidity
function recover(bytes32 hash, uint8 v, bytes32 r, bytes32 s) internal pure returns (address)
```

### toEthSignedMessageHash

```solidity
function toEthSignedMessageHash(bytes32 hash) internal pure returns (bytes32)
```

### toEthSignedMessageHash

```solidity
function toEthSignedMessageHash(bytes s) internal pure returns (bytes32)
```

### toTypedDataHash

```solidity
function toTypedDataHash(bytes32 domainSeparator, bytes32 structHash) internal pure returns (bytes32)
```
