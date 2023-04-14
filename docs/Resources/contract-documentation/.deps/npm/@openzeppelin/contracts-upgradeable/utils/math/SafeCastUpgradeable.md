## SafeCastUpgradeable

\_Wrappers over Solidity's uintXX/intXX casting operators with added overflow
checks.

Downcasting from uint256/int256 in Solidity does not revert on overflow. This can
easily result in undesired exploitation or bugs, since developers usually
assume that overflows raise errors. `SafeCast` restores this intuition by
reverting the transaction when such an operation overflows.

Using this library instead of the unchecked operations eliminates an entire
class of bugs, so it's recommended to use it always.

Can be combined with {SafeMath} and {SignedSafeMath} to extend it to smaller types, by performing
all math on `uint256` and `int256` and then downcasting.\_

### toUint248

```solidity
function toUint248(uint256 value) internal pure returns (uint248)
```

### toUint240

```solidity
function toUint240(uint256 value) internal pure returns (uint240)
```

### toUint232

```solidity
function toUint232(uint256 value) internal pure returns (uint232)
```

### toUint224

```solidity
function toUint224(uint256 value) internal pure returns (uint224)
```

### toUint216

```solidity
function toUint216(uint256 value) internal pure returns (uint216)
```

### toUint208

```solidity
function toUint208(uint256 value) internal pure returns (uint208)
```

### toUint200

```solidity
function toUint200(uint256 value) internal pure returns (uint200)
```

### toUint192

```solidity
function toUint192(uint256 value) internal pure returns (uint192)
```

### toUint184

```solidity
function toUint184(uint256 value) internal pure returns (uint184)
```

### toUint176

```solidity
function toUint176(uint256 value) internal pure returns (uint176)
```

### toUint168

```solidity
function toUint168(uint256 value) internal pure returns (uint168)
```

### toUint160

```solidity
function toUint160(uint256 value) internal pure returns (uint160)
```

### toUint152

```solidity
function toUint152(uint256 value) internal pure returns (uint152)
```

### toUint144

```solidity
function toUint144(uint256 value) internal pure returns (uint144)
```

### toUint136

```solidity
function toUint136(uint256 value) internal pure returns (uint136)
```

### toUint128

```solidity
function toUint128(uint256 value) internal pure returns (uint128)
```

### toUint120

```solidity
function toUint120(uint256 value) internal pure returns (uint120)
```

### toUint112

```solidity
function toUint112(uint256 value) internal pure returns (uint112)
```

### toUint104

```solidity
function toUint104(uint256 value) internal pure returns (uint104)
```

### toUint96

```solidity
function toUint96(uint256 value) internal pure returns (uint96)
```

### toUint88

```solidity
function toUint88(uint256 value) internal pure returns (uint88)
```

### toUint80

```solidity
function toUint80(uint256 value) internal pure returns (uint80)
```

### toUint72

```solidity
function toUint72(uint256 value) internal pure returns (uint72)
```

### toUint64

```solidity
function toUint64(uint256 value) internal pure returns (uint64)
```

### toUint56

```solidity
function toUint56(uint256 value) internal pure returns (uint56)
```

### toUint48

```solidity
function toUint48(uint256 value) internal pure returns (uint48)
```

### toUint40

```solidity
function toUint40(uint256 value) internal pure returns (uint40)
```

### toUint32

```solidity
function toUint32(uint256 value) internal pure returns (uint32)
```

### toUint24

```solidity
function toUint24(uint256 value) internal pure returns (uint24)
```

### toUint16

```solidity
function toUint16(uint256 value) internal pure returns (uint16)
```

### toUint8

```solidity
function toUint8(uint256 value) internal pure returns (uint8)
```

### toUint256

```solidity
function toUint256(int256 value) internal pure returns (uint256)
```

### toInt248

```solidity
function toInt248(int256 value) internal pure returns (int248 downcasted)
```

### toInt240

```solidity
function toInt240(int256 value) internal pure returns (int240 downcasted)
```

### toInt232

```solidity
function toInt232(int256 value) internal pure returns (int232 downcasted)
```

### toInt224

```solidity
function toInt224(int256 value) internal pure returns (int224 downcasted)
```

### toInt216

```solidity
function toInt216(int256 value) internal pure returns (int216 downcasted)
```

### toInt208

```solidity
function toInt208(int256 value) internal pure returns (int208 downcasted)
```

### toInt200

```solidity
function toInt200(int256 value) internal pure returns (int200 downcasted)
```

### toInt192

```solidity
function toInt192(int256 value) internal pure returns (int192 downcasted)
```

### toInt184

```solidity
function toInt184(int256 value) internal pure returns (int184 downcasted)
```

### toInt176

```solidity
function toInt176(int256 value) internal pure returns (int176 downcasted)
```

### toInt168

```solidity
function toInt168(int256 value) internal pure returns (int168 downcasted)
```

### toInt160

```solidity
function toInt160(int256 value) internal pure returns (int160 downcasted)
```

### toInt152

```solidity
function toInt152(int256 value) internal pure returns (int152 downcasted)
```

### toInt144

```solidity
function toInt144(int256 value) internal pure returns (int144 downcasted)
```

### toInt136

```solidity
function toInt136(int256 value) internal pure returns (int136 downcasted)
```

### toInt128

```solidity
function toInt128(int256 value) internal pure returns (int128 downcasted)
```

### toInt120

```solidity
function toInt120(int256 value) internal pure returns (int120 downcasted)
```

### toInt112

```solidity
function toInt112(int256 value) internal pure returns (int112 downcasted)
```

### toInt104

```solidity
function toInt104(int256 value) internal pure returns (int104 downcasted)
```

### toInt96

```solidity
function toInt96(int256 value) internal pure returns (int96 downcasted)
```

### toInt88

```solidity
function toInt88(int256 value) internal pure returns (int88 downcasted)
```

### toInt80

```solidity
function toInt80(int256 value) internal pure returns (int80 downcasted)
```

### toInt72

```solidity
function toInt72(int256 value) internal pure returns (int72 downcasted)
```

### toInt64

```solidity
function toInt64(int256 value) internal pure returns (int64 downcasted)
```

### toInt56

```solidity
function toInt56(int256 value) internal pure returns (int56 downcasted)
```

### toInt48

```solidity
function toInt48(int256 value) internal pure returns (int48 downcasted)
```

### toInt40

```solidity
function toInt40(int256 value) internal pure returns (int40 downcasted)
```

### toInt32

```solidity
function toInt32(int256 value) internal pure returns (int32 downcasted)
```

### toInt24

```solidity
function toInt24(int256 value) internal pure returns (int24 downcasted)
```

### toInt16

```solidity
function toInt16(int256 value) internal pure returns (int16 downcasted)
```

### toInt8

```solidity
function toInt8(int256 value) internal pure returns (int8 downcasted)
```

### toInt256

```solidity
function toInt256(uint256 value) internal pure returns (int256)
```
