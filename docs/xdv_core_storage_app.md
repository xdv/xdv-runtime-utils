# XdvCoreStorageApp

- Source: `xdv-runtime-utils/src/xdv_core_storage_app.ds`
- App ID: `11`
- Summary: xdv-core: storage and filesystem administration application

## Purpose
xdv-core: storage and filesystem administration application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `storage_status` | `(none)` | Performs storage status operation. |
| `storage_partition_print` | `device: Str` | Performs storage partition print operation. |
| `storage_mkfs` | `device: Str` | Performs storage mkfs operation. |
| `storage_fsck` | `device: Str` | Performs storage fsck operation. |
| `storage_mount` | `device: Str, mount_point: Str` | Performs storage mount operation. |
| `storage_unmount` | `mount_point: Str` | Performs storage unmount operation. |
| `storage_df` | `device: Str, mount_point: Str` | Performs storage df operation. |
| `storage_dir_list` | `path: Str` | Performs storage dir list operation. |
| `storage_file_touch` | `path: Str` | Performs storage file touch operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_STORAGE_FAILED` (`UInt32`): `1`

## Operational Constants
- `APP_ID` (`UInt32`): `11`
- `SAFE_REPAIR_MODE` (`UInt32`): `1`
- `DEFAULT_FILE_MODE` (`UInt16`): `420`

## Runtime Dependencies
- Detected runtime/API call usage:
- `dir_ls(...)`
- `fdisk_print(...)`
- `file_touch(...)`
- `fsck_xdvfs(...)`
- `lsblk(...)`
- `mkfs_xdvfs(...)`
- `mount_umount(...)`
- `mount_xdvfs(...)`
- `perm_chmod(...)`
- `probe_all(...)`
- `space_df(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across these modules is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = storage_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```
