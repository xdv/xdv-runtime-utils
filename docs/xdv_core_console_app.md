# XdvCoreConsoleApp

- Source: `xdv-runtime-utils/src/xdv_core_console_app.ds`
- App ID: `1`
- Summary: xdv-core: console administration application

## Purpose
xdv-core: console administration application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `console_status` | `(none)` | Performs console status operation. |
| `console_clear` | `(none)` | Performs console clear operation. |
| `console_set_theme` | `fg: UInt8, bg: UInt8` | Performs console set theme operation. |
| `console_reset_theme` | `(none)` | Performs console reset theme operation. |
| `console_write` | `ptr: UInt64` | Performs console write operation. |
| `console_read_key` | `(none)` | Performs console read key operation. |
| `console_move_cursor` | `row: UInt32, col: UInt32` | Performs console move cursor operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_CONSOLE_FAIL` (`UInt32`): `1`
- `STATUS_INVALID_COORD` (`UInt32`): `2`
- `STATUS_INVALID_INPUT` (`UInt32`): `3`

## Operational Constants
- `APP_ID` (`UInt32`): `1`
- `DEFAULT_FG` (`UInt8`): `7`
- `DEFAULT_BG` (`UInt8`): `0`
- `MAX_ROWS` (`UInt32`): `25`
- `MAX_COLS` (`UInt32`): `80`

## Runtime Dependencies
- Detected runtime/API call usage:
- `clear(...)`
- `get_cursor_col(...)`
- `get_cursor_row(...)`
- `getchar(...)`
- `puts(...)`
- `set_color(...)`
- `set_cursor(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across these modules is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = console_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```
