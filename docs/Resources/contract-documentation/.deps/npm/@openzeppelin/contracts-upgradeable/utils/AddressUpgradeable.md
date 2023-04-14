## AddressUpgradeable

_Collection of functions related to the address type_

### isContract

```solidity
function isContract(address account) internal view returns (bool)
```

### sendValue

```solidity
function sendValue(address payable recipient, uint256 amount) internal
```

### functionCall

```solidity
function functionCall(address target, bytes data) internal returns (bytes)
```

### functionCall

```solidity
function functionCall(address target, bytes data, string errorMessage) internal returns (bytes)
```

### functionCallWithValue

```solidity
function functionCallWithValue(address target, bytes data, uint256 value) internal returns (bytes)
```

### functionCallWithValue

```solidity
function functionCallWithValue(address target, bytes data, uint256 value, string errorMessage) internal returns (bytes)
```

### functionStaticCall

```solidity
function functionStaticCall(address target, bytes data) internal view returns (bytes)
```

### functionStaticCall

```solidity
function functionStaticCall(address target, bytes data, string errorMessage) internal view returns (bytes)
```

### verifyCallResultFromTarget

```solidity
function verifyCallResultFromTarget(address target, bool success, bytes returndata, string errorMessage) internal view returns (bytes)
```

### verifyCallResult

```solidity
function verifyCallResult(bool success, bytes returndata, string errorMessage) internal pure returns (bytes)
```
