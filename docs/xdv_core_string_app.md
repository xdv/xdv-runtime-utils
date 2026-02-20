# XdvCoreStringApp

- Source: `xdv-runtime-utils/src/xdv_core_string_app.ds`
- App ID: `7`
- Summary: xdv-core: runtime string administration application

## Purpose
xdv-core: runtime string administration application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `string_len` | `ptr: UInt64` | Performs string len operation. |
| `string_concat` | `a: UInt64, b: UInt64` | Performs string concat operation. |
| `string_compare` | `a: UInt64, b: UInt64` | Performs string compare operation. |
| `string_find` | `haystack: UInt64, needle: UInt64` | Performs string find operation. |
| `string_substring` | `ptr: UInt64, start_idx: UInt32, end_idx: UInt32` | Performs string substring operation. |
| `string_to_upper` | `ptr: UInt64` | Performs string to upper operation. |
| `string_to_lower` | `ptr: UInt64` | Performs string to lower operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_STRING_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`
- `STATUS_OUT_OF_BOUNDS` (`UInt32`): `3`

## Operational Constants
- `APP_ID` (`UInt32`): `7`

## Runtime Dependencies
- Detected runtime/API call usage:
- `compare(...)`
- `concat(...)`
- `find(...)`
- `len(...)`
- `substring(...)`
- `to_lower(...)`
- `to_upper(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across these modules is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = string_len();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```
