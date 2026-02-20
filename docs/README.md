# xdv-runtime-utils Application Documentation

This directory contains markdown documentation for each application module in `xdv-runtime-utils/src`.

| App Module | Forge | Procedures | Summary |
|---|---|---:|---|
| `xdv_core_cli.ds` | `XdvCoreCli` | 5 | xdv-core: shared CLI orchestration entrypoints |
| `xdv_core_console_app.ds` | `XdvCoreConsoleApp` | 7 | xdv-core: console administration application |
| `xdv_core_init_app.ds` | `XdvCoreInitApp` | 7 | xdv-core: init lifecycle administration application |
| `xdv_core_io_app.ds` | `XdvCoreIoApp` | 6 | xdv-core: runtime I/O administration application |
| `xdv_core_log_app.ds` | `XdvCoreLogApp` | 6 | xdv-core: logging administration application |
| `xdv_core_memory_app.ds` | `XdvCoreMemoryApp` | 6 | xdv-core: runtime memory administration application |
| `xdv_core_process_app.ds` | `XdvCoreProcessApp` | 7 | xdv-core: runtime process administration application |
| `xdv_core_recovery_app.ds` | `XdvCoreRecoveryApp` | 4 | xdv-core: diagnostics and recovery application |
| `xdv_core_runtime_admin.ds` | `XdvCoreRuntimeAdmin` | 3 | xdv-core: runtime administration orchestration application |
| `xdv_core_scheduler_app.ds` | `XdvCoreSchedulerApp` | 7 | xdv-core: runtime scheduler administration application |
| `xdv_core_security_app.ds` | `XdvCoreSecurityApp` | 6 | xdv-core: security and permission administration application |
| `xdv_core_service_app.ds` | `XdvCoreServiceApp` | 6 | xdv-core: service and task control application |
| `xdv_core_storage_app.ds` | `XdvCoreStorageApp` | 9 | xdv-core: storage and filesystem administration application |
| `xdv_core_string_app.ds` | `XdvCoreStringApp` | 7 | xdv-core: runtime string administration application |
| `xdv_core_sysmon_app.ds` | `XdvCoreSysmonApp` | 4 | xdv-core: runtime and system telemetry application |

## Notes
- Generated from source signatures/constants in `xdv-runtime-utils/src`.
- Update docs after API changes to keep signatures and status codes in sync.
- `xdv_core_command_profile.ds` is intentionally excluded because it is not an app module.
