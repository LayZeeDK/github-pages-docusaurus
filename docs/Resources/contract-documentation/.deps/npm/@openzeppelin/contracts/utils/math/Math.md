## Math

_Standard math utilities missing in the Solidity language._

### Rounding

```solidity
enum Rounding {
  Down,
  Up,
  Zero
}
```

### max

```solidity
function max(uint256 a, uint256 b) internal pure returns (uint256)
```

### min

```solidity
function min(uint256 a, uint256 b) internal pure returns (uint256)
```

### average

```solidity
function average(uint256 a, uint256 b) internal pure returns (uint256)
```

### ceilDiv

```solidity
function ceilDiv(uint256 a, uint256 b) internal pure returns (uint256)
```

### mulDiv

```solidity
function mulDiv(uint256 x, uint256 y, uint256 denominator) internal pure returns (uint256 result)
```

Calculates floor(x \* y / denominator) with full precision. Throws if result overflows a uint256 or denominator == 0

### mulDiv

```solidity
function mulDiv(uint256 x, uint256 y, uint256 denominator, enum Math.Rounding rounding) internal pure returns (uint256)
```

Calculates x \* y / denominator with full precision, following the selected rounding direction.

### sqrt

```solidity
function sqrt(uint256 a) internal pure returns (uint256)
```

### sqrt

```solidity
function sqrt(uint256 a, enum Math.Rounding rounding) internal pure returns (uint256)
```

Calculates sqrt(a), following the selected rounding direction.

### log2

```solidity
function log2(uint256 value) internal pure returns (uint256)
```

### log2

```solidity
function log2(uint256 value, enum Math.Rounding rounding) internal pure returns (uint256)
```

### log10

```solidity
function log10(uint256 value) internal pure returns (uint256)
```

### log10

```solidity
function log10(uint256 value, enum Math.Rounding rounding) internal pure returns (uint256)
```

### log256

```solidity
function log256(uint256 value) internal pure returns (uint256)
```

### log256

```solidity
function log256(uint256 value, enum Math.Rounding rounding) internal pure returns (uint256)
```
