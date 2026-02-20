# XdvCoreSysmonApp

- Source: `xdv-runtime-utils/src/xdv_core_sysmon_app.ds`
- App ID: `8`
- Summary: xdv-core: runtime and system telemetry application

## Purpose
xdv-core: runtime and system telemetry application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `sysmon_snapshot` | `(none)` | Performs sysmon snapshot operation. |
| `sysmon_runtime_health` | `(none)` | Performs sysmon runtime health operation. |
| `sysmon_io_sample` | `path_ptr: UInt64, buffer_ptr: UInt64` | Performs sysmon io sample operation. |
| `sysmon_storage_sample` | `device: Str` | Performs sysmon storage sample operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_SYSMON_FAILED` (`UInt32`): `1`
- `STATUS_IO_SAMPLE_FAILED` (`UInt32`): `2`
- `STATUS_STORAGE_SAMPLE_FAILED` (`UInt32`): `3`

## Operational Constants
- `APP_ID` (`UInt32`): `8`
- `SAMPLE_BUFFER_SIZE` (`UInt32`): `256`

## Runtime Dependencies
- Detected runtime/API call usage:
- `init_status(...)`
- `io_close(...)`
- `io_open_read(...)`
- `io_read(...)`
- `lsblk(...)`
- `memory_diag(...)`
- `probe_all(...)`
- `process_current_pid(...)`
- `process_yield(...)`
- `scheduler_status(...)`
- `scheduler_tick(...)`
- `space_iostat(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across these modules is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = sysmon_snapshot();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```
