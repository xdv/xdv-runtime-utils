# XdvCoreServiceApp

- Source: `xdv-runtime-utils/src/xdv_core_service_app.ds`
- App ID: `9`
- Summary: xdv-core: service and task control application

## Purpose
xdv-core: service and task control application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `service_status` | `(none)` | Performs service status operation. |
| `service_start` | `entry: UInt64` | Performs service start operation. |
| `service_start_priority` | `entry: UInt64, priority: UInt32` | Performs service start priority operation. |
| `service_stop` | `pid: UInt32` | Performs service stop operation. |
| `service_restart` | `pid: UInt32, entry: UInt64` | Performs service restart operation. |
| `service_reload` | `(none)` | Performs service reload operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_SERVICE_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_PID` (`UInt32`): `2`

## Operational Constants
- `APP_ID` (`UInt32`): `9`
- `DEFAULT_STACK_SIZE` (`UInt32`): `8192`
- `DEFAULT_PRIORITY` (`UInt32`): `5`
- `INVALID_PID` (`UInt32`): `0`

## Runtime Dependencies
- Detected runtime/API call usage:
- `init_reload(...)`
- `process_current_pid(...)`
- `process_kill(...)`
- `process_spawn_with_stack(...)`
- `scheduler_add(...)`
- `scheduler_remove(...)`
- `scheduler_set_priority(...)`
- `scheduler_status(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across these modules is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = service_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```
