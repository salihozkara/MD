# Database Tables

This documentation describes all database tables and their purposes. You can read this documentation to get an overall knowledge of the database tables that comes from different modules.

## [Audit Logging Module](Audit-Logging.md)

### AbpAuditLogs

#### Description

This table stores information about the audit logs in the application. Each record represents an audit log and tracks the actions performed in the application.

---

### AbpAuditLogActions

#### Description

This table stores information about the actions performed in the application, which are logged for auditing purposes.

#### Uses

| Table | Column | Description |
| --- | --- | --- |
| [AbpAuditLogs](#abpauditlogs) | Id | Links each action to a specific audit log. |

---

### AbpEntityChanges

#### Description

This table stores information about entity changes in the application.

#### Uses

| Table | Column | Description |
| --- | --- | --- |
| [AbpAuditLogs](#abpauditlogs) | Id | Links each entity change to a specific audit log. |

---

### AbpEntityPropertyChanges

#### Description

This table stores information about property changes to entities in the application.

## Uses

| Table | Column | Description |
| --- | --- | --- |
| [AbpEntityChanges](#abpentitychanges) | Id | 	To associate the property change with the corresponding entity change. |

---

## [Background Jobs Module](Background-Jobs.md)

### AbpBackgroundJobs

#### Description

This table stores information about the background jobs in the application and facilitates their efficient management and tracking. Each entry in the table contains details of a background job, including job name, arguments, try count, next try time, last try time, abandoned status, and priority.

---

## [Tenant Management Module](Tenant-Management.md)

### AbpTenants

#### Description

This table stores information about the tenants.

---

### AbpTenantConnectionStrings

#### Description

This table stores information about the tenant database connection strings.

## Uses

| Table | Column | Description |
| --- | --- | --- |
| [AbpTenants](#AbpTenants) | Id | The `Id` column in the `AbpTenants` table is used to associate the tenant connection string with the corresponding tenant. |

---

## Blogging Module

### BlgUsers

#### Description

This table stores information about the blog users.

---

### BlgBlogs

#### Description

This table stores information about the blogs.

---

### BlgPosts

#### Description

This table stores information about the blog posts.

#### Uses

| Table | Column | Description |
| --- | --- | --- |
| [BlgBlogs](#blgblogs) | Id | To associate the blog post with the corresponding blog. |
---

### BlgComments
#### Description

This table stores information about comments made on blog posts.
#### Uses

| Table | Column | Description |
| --- | --- | --- |
| [BlgPosts](#blgposts) | Id | Links the comment to the corresponding blog post. |
| [BlgComments](#blgcomments) | Id | Links the comment to the parent comment. |

---

### BlgTags
#### Description

This table stores information about the tags.

---

### BlgPostTags

#### Description

This table stores information about the post tags.

#### Uses

| Table | Column | Description |
| --- | --- | --- |
| [BlgTags](#blgtags) | Id | Links the post tag to the corresponding tag. |
| [BlgPosts](#blgposts) | Id | Links the post tag to the corresponding blog post. |

---

## [CMS Kit Module](Cms-Kit/Index.md)

### CmsUsers

#### Description

This table stores information about the cms kit module users.

---

### CmsBlogs

#### Description

This table stores information about the blogs.

---

### CmsBlogPosts

#### Description

This table stores information about the blog posts.

#### Uses

| Table | Column | Description |
| --- | --- | --- |
| [CmsUsers](#cmsusers) | Id | Links the blog post to the corresponding author. |

---

### CmsBlogFeatures

#### Description

This table stores information about the blog features.

---

### CmsComments

#### Description

This table is used to store the comments and their relations with entities. The table is used by the CmsComments component.

---

### CmsTags

#### Description

This table stores information about the tags.

---

### CmsEntityTags

#### Description

This table is used to store the tags and their relations with entities. The table is used by the CmsTags component.

---

### CmsGlobalResources

#### Description

This table stores information about the global resources.

---

### CmsMediaDescriptors

#### Description

This table stores information about the media descriptors. 

---

### CmsMenuItems

#### Description

This table stores information about the menu items.

---

### CmsPages

#### Description

This table stores the pages in the application.

---
