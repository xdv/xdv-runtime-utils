# XdvCoreProcessApp

- Source: `xdv-runtime-utils/src/xdv_core_process_app.ds`
- App ID: `5`
- Summary: xdv-core: runtime process administration application

## Purpose
xdv-core: runtime process administration application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `process_spawn` | `entry: UInt64` | Performs process spawn operation. |
| `process_spawn_with_stack` | `entry: UInt64, stack_size: UInt32` | Performs process spawn with stack operation. |
| `process_join` | `pid: UInt32` | Performs process join operation. |
| `process_kill` | `pid: UInt32` | Performs process kill operation. |
| `process_sleep` | `ms: UInt32` | Performs process sleep operation. |
| `process_yield` | `(none)` | Performs process yield operation. |
| `process_current_pid` | `(none)` | Performs process current pid operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_PROCESS_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_PID` (`UInt32`): `2`

## Operational Constants
- `APP_ID` (`UInt32`): `5`
- `DEFAULT_STACK_SIZE` (`UInt32`): `8192`
- `DEFAULT_EXIT_CODE` (`UInt32`): `0`
- `INVALID_PID` (`UInt32`): `0`

## Runtime Dependencies
- Detected runtime/API call usage:
- `exit(...)`
- `getpid(...)`
- `join(...)`
- `sleep(...)`
- `spawn(...)`
- `yield(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across these modules is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = process_spawn();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```
