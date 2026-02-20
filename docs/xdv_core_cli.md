# XdvCoreCli

- Source: `xdv-runtime-utils/src/xdv_core_cli.ds`
- Summary: xdv-core: shared CLI orchestration entrypoints

## Purpose
xdv-core: shared CLI orchestration entrypoints

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `run_minimum` | `(none)` | Executes minimum workflow. |
| `run_admin` | `(none)` | Executes admin workflow. |
| `run_recovery` | `device: Str, mount_point: Str` | Executes recovery workflow. |
| `run_all` | `device: Str, mount_point: Str` | Executes all workflow. |
| `run_profile` | `profile: UInt32, device: Str, mount_point: Str` | Executes profile workflow. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_PROFILE_INVALID` (`UInt32`): `1`
- `STATUS_PROFILE_FAILED` (`UInt32`): `2`

## Operational Constants
- `PROFILE_MINIMUM` (`UInt32`): `1`
- `PROFILE_ADMIN` (`UInt32`): `2`
- `PROFILE_RECOVERY` (`UInt32`): `3`
- `PROFILE_ALL` (`UInt32`): `4`

## Runtime Dependencies
- Detected runtime/API call usage:
- `recovery_diagnostics(...)`
- `recovery_repair(...)`
- `recovery_safe_mode(...)`
- `run_runtime_minimum_set(...)`
- `run_system_admin_set(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across these modules is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = run_minimum();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```
