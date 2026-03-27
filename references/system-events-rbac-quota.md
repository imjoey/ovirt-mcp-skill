# 目录索引

| 分类 | 工具数 | 页码 |
|------|--------|------|
| [System & Jobs](#system--jobs) | 6 | 2 |
| [Events](#events) | 12 | 2 |
| [RBAC Users](#rbac-users) | 6 | 3 |
| [RBAC Groups](#rbac-groups) | 2 | 4 |
| [RBAC Roles](#rbac-roles) | 5 | 4 |
| [RBAC Permissions](#rbac-permissions) | 3 | 5 |
| [RBAC Tags](#rbac-tags) | 7 | 5 |
| [RBAC Filters](#rbac-filters) | 1 | 6 |
| [Quota](#quota) | 7 | 6 |
| [Affinity Groups](#affinity-groups) | 7 | 6 |
| [Affinity Labels](#affinity-labels) | 6 | 7 |

---

## System & Jobs

### system_get
获取系统信息

**参数：**（无参数）

---

### system_option_list
列出系统选项

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `category` | string | 否 | 选项分类（可选） |

---

### job_list
列出任务

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `page` | number | 否 | 页码 |
| `page_size` | number | 否 | 每页数量 |

---

### job_get
获取任务详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `job_id` | string | **是** | 任务 ID |

---

### job_cancel
取消任务

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `job_id` | string | **是** | 任务 ID |
| `force` | boolean | 否 | 强制取消 |

---

### system_statistics
获取系统统计信息

**参数：**（无参数）

---

## Events

### event_list
列出事件

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `search` | string | 否 | 搜索条件（可选） |
| `severity` | string | 否 | 严重级别过滤（error/warning/info/alert） |
| `page` | number | 否 | 页码，默认 1 |
| `page_size` | number | 否 | 每页数量，默认 50 |

---

### event_get
获取事件详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `event_id` | string | **是** | 事件 ID |

---

### event_search
搜索事件

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `query` | string | **是** | 搜索查询 |
| `page` | number | 否 | 页码，默认 1 |
| `page_size` | number | 否 | 每页数量，默认 50 |

---

### event_alerts
获取告警事件

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `page` | number | 否 | 页码，默认 1 |
| `page_size` | number | 否 | 每页数量，默认 50 |

---

### event_errors
获取错误事件

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `page` | number | 否 | 页码，默认 1 |
| `page_size` | number | 否 | 每页数量，默认 50 |

---

### event_warnings
获取警告事件

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `page` | number | 否 | 页码，默认 1 |
| `page_size` | number | 否 | 每页数量，默认 50 |

---

### event_summary
获取事件统计摘要

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `hours` | number | 否 | 统计最近 N 小时，默认 24 |

---

### event_acknowledge
确认事件

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `event_id` | string | **是** | 事件 ID |

---

### event_clear_alerts
清除告警事件

**参数：**（无参数）

---

### event_subscription_list
列出事件订阅

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `user` | string | 否 | 用户名称（可选） |

---

### bookmark_list
列出书签

**参数：**（无参数）

---

## RBAC Users

### user_list
列出用户

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `search` | string | 否 | 搜索条件（可选） |

---

### user_get
获取用户详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 用户名称或 ID |

---

### user_create
创建用户

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `username` | string | **是** | 用户名 |
| `email` | string | 否 | 邮箱 |
| `first_name` | string | 否 | 名 |
| `last_name` | string | 否 | 姓 |

---

### user_update
更新用户

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 用户名称或 ID |
| `email` | string | 否 | 新邮箱 |
| `first_name` | string | 否 | 新名 |
| `last_name` | string | 否 | 新姓 |

---

### user_delete
删除用户

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 用户名称或 ID |

---

### user_groups
列出用户所属的组

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 用户名称或 ID |

---

## RBAC Groups

### group_list
列出用户组

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `search` | string | 否 | 搜索条件（可选） |

---

### group_get
获取用户组详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 组名称或 ID |

---

## RBAC Roles

### role_list
列出角色

**参数：**（无参数）

---

### role_get
获取角色详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 角色名称或 ID |

---

### role_create
创建角色

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 角色名称 |
| `description` | string | 否 | 描述（可选） |
| `administrative` | boolean | 否 | 是否为管理员角色，默认 false |
| `permit_ids` | string[] | 否 | 权限 ID 列表 |

---

### role_update
更新角色

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 角色名称或 ID |
| `new_name` | string | 否 | 新名称 |
| `description` | string | 否 | 新描述 |

---

### role_delete
删除角色

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 角色名称或 ID |

---

## RBAC Permissions

### permit_list
列出所有权限单元

**参数：**（无参数）

---

### permission_list
列出资源的权限

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `resource_type` | string | **是** | 资源类型（vm/host/cluster/datacenter/network/storagedomain/template） |
| `resource_id` | string | **是** | 资源 ID 或名称 |

---

### permission_assign
分配权限

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `resource_type` | string | **是** | 资源类型（vm/host/cluster/datacenter/network/storagedomain/template） |
| `resource_id` | string | **是** | 资源 ID 或名称 |
| `user_or_group` | string | **是** | 主体类型（user 或 group） |
| `role_name` | string | **是** | 角色名称或 ID |
| `principal_name` | string | **是** | 用户名或组名 |

---

### permission_revoke
撤销权限

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `resource_type` | string | **是** | 资源类型 |
| `resource_id` | string | **是** | 资源 ID 或名称 |
| `permission_id` | string | **是** | 权限 ID |

---

## RBAC Tags

### tag_list
列出所有标签

**参数：**（无参数）

---

### tag_create
创建标签

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 标签名称 |
| `description` | string | 否 | 描述（可选） |
| `parent_name` | string | 否 | 父标签名称（可选） |

---

### tag_delete
删除标签

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 标签名称或 ID |

---

### tag_assign
为资源分配标签

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `resource_type` | string | **是** | 资源类型（vm/host/cluster/datacenter/network/storagedomain/template） |
| `resource_id` | string | **是** | 资源 ID 或名称 |
| `tag_name` | string | **是** | 标签名称或 ID |

---

### tag_unassign
移除资源的标签

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `resource_type` | string | **是** | 资源类型 |
| `resource_id` | string | **是** | 资源 ID 或名称 |
| `tag_name` | string | **是** | 标签名称或 ID |

---

### tag_list_resources
列出资源的标签

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `resource_type` | string | **是** | 资源类型 |
| `resource_id` | string | **是** | 资源 ID 或名称 |

---

## RBAC Filters

### filter_list
列出权限过滤器

**参数：**（无参数）

---

## Quota

### quota_list
列出数据中心的配额

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `datacenter` | string | **是** | 数据中心名称或 ID |

---

### quota_get
获取配额详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `datacenter` | string | **是** | 数据中心名称或 ID |
| `name_or_id` | string | **是** | 配额名称或 ID |

---

### quota_create
创建配额

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 配额名称 |
| `datacenter` | string | **是** | 数据中心名称 |
| `description` | string | 否 | 描述 |
| `cluster_hard_limit_pct` | number | 否 | 集群硬限制百分比 |
| `storage_hard_limit_pct` | number | 否 | 存储硬限制百分比 |

---

### quota_update
更新配额

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `datacenter` | string | **是** | 数据中心名称或 ID |
| `name_or_id` | string | **是** | 配额名称或 ID |
| `new_name` | string | 否 | 新名称 |
| `description` | string | 否 | 新描述 |
| `cluster_hard_limit_pct` | number | 否 | 集群硬限制百分比 |
| `storage_hard_limit_pct` | number | 否 | 存储硬限制百分比 |

---

### quota_delete
删除配额

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `datacenter` | string | **是** | 数据中心名称或 ID |
| `name_or_id` | string | **是** | 配额名称或 ID |

---

### quota_cluster_limit_list
列出配额的集群限制

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `datacenter` | string | **是** | 数据中心名称或 ID |
| `name_or_id` | string | **是** | 配额名称或 ID |

---

### quota_storage_limit_list
列出配额的存储限制

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `datacenter` | string | **是** | 数据中心名称或 ID |
| `name_or_id` | string | **是** | 配额名称或 ID |

---

## Affinity Groups

### affinity_group_list
列出亲和性组

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | **是** | 集群名称 |

---

### affinity_group_get
获取亲和性组详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | **是** | 集群名称 |
| `name_or_id` | string | **是** | 亲和性组名称或 ID |

---

### affinity_group_create
创建亲和性组

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 亲和性组名称 |
| `cluster` | string | **是** | 集群名称 |
| `positive` | boolean | 否 | True=亲和性，False=反亲和性，默认 True |
| `enforcing` | boolean | 否 | True=强制执行，False=软性规则，默认 False |
| `vms` | string[] | 否 | VM 名称或 ID 列表 |

---

### affinity_group_update
更新亲和性组

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | **是** | 集群名称 |
| `name_or_id` | string | **是** | 亲和性组名称或 ID |
| `new_name` | string | 否 | 新名称（可选） |
| `positive` | boolean | 否 | True=亲和性，False=反亲和性 |
| `enforcing` | boolean | 否 | True=强制执行，False=软性规则 |

---

### affinity_group_delete
删除亲和性组

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | **是** | 集群名称 |
| `name_or_id` | string | **是** | 亲和性组名称或 ID |

---

### affinity_group_add_vm
添加 VM 到亲和性组

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | **是** | 集群名称 |
| `affinity_group` | string | **是** | 亲和性组名称或 ID |
| `vm` | string | **是** | VM 名称或 ID |

---

### affinity_group_remove_vm
从亲和性组移除 VM

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | **是** | 集群名称 |
| `affinity_group` | string | **是** | 亲和性组名称或 ID |
| `vm` | string | **是** | VM 名称或 ID |

---

## Affinity Labels

### affinity_label_list
列出亲和性标签

**参数：**（无参数）

---

### affinity_label_get
获取亲和性标签详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 标签名称或 ID |

---

### affinity_label_create
创建亲和性标签

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 标签名称 |

---

### affinity_label_delete
删除亲和性标签

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 标签名称或 ID |

---

### affinity_label_assign
为资源分配亲和性标签

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `label` | string | **是** | 标签名称或 ID |
| `resource_type` | string | **是** | 资源类型（vm 或 host） |
| `resource` | string | **是** | 资源名称或 ID |

---

### affinity_label_unassign
移除资源的亲和性标签

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `label` | string | **是** | 标签名称或 ID |
| `resource_type` | string | **是** | 资源类型（vm 或 host） |
| `resource` | string | **是** | 资源名称或 ID |
