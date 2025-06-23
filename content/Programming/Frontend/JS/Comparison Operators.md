1. == (Double equals) is for **loose equality**. Returns true for somewhat logically equal operands.
	This is because their types are converted to same type before comparing.
2. === (Triple equals) is for **strict equality**. Returns true if both operands are same type and value.
3.  != is for **loose inequality**. Performs type coercion like `==`
4. !== is for **strict inequality**. Both type and value are involved. 

> [!NOTE] Predictable Behavior
> **Recommended** to use `===` in most cases

### Further comparison

| Operator | Description                                                        | Example      | Result  |
| -------- | ------------------------------------------------------------------ | ------------ | ------- |
| `==`     | Converts operands to the same type before comparing.               | `1 == '1'`   | `true`  |
| `==`     | Converts `true` to `1` and `false` to `0` before comparing.        | `true == 1`  | `true`  |
| `==`     | Converts operands to numbers if one is a number.                   | `0 == false` | `true`  |
| `===`    | Strict Equality: No type conversion, compares both value and type. | `1 === '1'`  | `false` |
| `===`    | Both operands must be of the same type and value.                  | `1 === 1`    | `true`  |
| `===`    | No type conversion; different types mean `false`.                  | `true === 1` | `false` |

### Confusing comparison

| Scenario                | `==` (Double Equals) | `===` (Triple Equals) |
| ----------------------- | -------------------- | --------------------- |
| `1` with `"1"`          | `true`               | `false`               |
| `0` with `""`           | `true`               | `false`               |
| `null` with `undefined` | `true`               | `false`               |
| `[1]` with `[1]`        | `false`              | `false`               |
| `({})` with `({})`      | `false`              | `false`               |

