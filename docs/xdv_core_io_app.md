# XdvCoreIoApp

- Source: `xdv-runtime-utils/src/xdv_core_io_app.ds`
- App ID: `3`
- Summary: xdv-core: runtime I/O administration application

## Purpose
xdv-core: runtime I/O administration application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `io_open_read` | `path_ptr: UInt64` | Performs io open read operation. |
| `io_open_write` | `path_ptr: UInt64` | Performs io open write operation. |
| `io_open_append` | `path_ptr: UInt64` | Performs io open append operation. |
| `io_read` | `fd: UInt64, buffer: UInt64, size: UInt32` | Performs io read operation. |
| `io_write` | `fd: UInt64, buffer: UInt64, size: UInt32` | Performs io write operation. |
| `io_close` | `fd: UInt64` | Performs io close operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_IO_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_PATH` (`UInt32`): `2`
- `STATUS_INVALID_HANDLE` (`UInt32`): `3`
- `STATUS_INVALID_BUFFER` (`UInt32`): `4`

## Operational Constants
- `APP_ID` (`UInt32`): `3`
- `MODE_READ` (`UInt32`): `0`
- `MODE_WRITE` (`UInt32`): `1`
- `MODE_APPEND` (`UInt32`): `2`
- `INVALID_FD` (`UInt64`): `0`

## Runtime Dependencies
- Detected runtime/API call usage:
- `close(...)`
- `open(...)`
- `read(...)`
- `write(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across these modules is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = io_open_read();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```
