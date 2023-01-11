## AbpAuditLogActions

AbpAuditLogActions is used to store audit log actions.

### Columns

| Key | Name | Data type | Nullable | Default value | Description | Reference |
| --- | --- | --- | --- | --- | --- | --- |
| Primary | Id | `Guid` | ❌ | Next value for Id | Id of the audit log action. |  |
|  | TenantId | `Guid?` | ✔ |  | Tenant id of the audit log action. |  |
|  | AuditLogId | `Guid` | ❌ |  | Id of the audit log. | [AuditLogs](AbpAuditLogs.md) |
|  | ServiceName | `nvarchar(256)` | ✔ |  | Service name of the audit log action. |  |
|  | MethodName | `nvarchar(128)` | ✔ |  | Method name of the audit log action. |  |
|  | Parameters | `nvarchar(2000)` | ✔ |  | Parameters of the audit log action. |  |
|  | ExecutionTime | `datetime2(7)` | ❌ |  | Execution time of the audit log action. |  |
|  | ExecutionDuration | `int` | ❌ |  | Execution duration of the audit log action. |  |
|  | ExtraProperties | `nvarchar(max)` | ✔ |  | Extra properties of the audit log action. |  |

### Relations

| Foreign table | Primary table | Join | Description |
| --- | --- | --- | --- |
| [AuditLogs](AbpAuditLogs.md) | AbpAuditLogActions | AuditLogId = Id |  |

### Uniques

| Key Name | Columns | Is primary key | Is clustered |
| --- | --- | --- | --- |
| PK_AbpAuditLogActions | Id | ✔ | ✔ |

### Uses

| Table | Column | Description |
| --- | --- | --- |
| [AuditLogs](AbpAuditLogs.md) | Id |  |

### Used by

| Table | Column | Description |
| --- | --- | --- |
| [AuditLogActions](AbpAuditLogActions.md) | AuditLogId |  |

### Indexes

| Name | Columns | Is unique | Filter |
| --- | --- | --- | --- |
| IX_AbpAuditLogActions_AuditLogId | AuditLogId |  |  |
| IX_AbpAuditLogActions_TenantId_ServiceName_MethodName_ExecutionTime | TenantId, ServiceName, MethodName, ExecutionTime |  |  |
| PK_AbpAuditLogActions | Id | ✔ |  |
