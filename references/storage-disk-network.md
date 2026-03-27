# 目录索引

| 分类 | 工具数 | 页码 |
|------|--------|------|
| [Storage Core](#storage-core) | 2 | 2 |
| [Storage Extended](#storage-extended) | 13 | 2 |
| [Disks Core](#disks-core) | 3 | 3 |
| [Disks Extended](#disks-extended) | 9 | 3 |
| [Networks](#networks) | 5 | 4 |
| [VNIC Profiles](#vnic-profiles) | 5 | 4 |
| [Network Filters & QoS](#network-filters--qos) | 3 | 5 |

---

## Storage Core

### storage_list
列出存储域

**参数：**（无参数）

---

### storage_attach
挂载存储

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `storage_name` | string | **是** | 存储域名称 |
| `dc_name` | string | **是** | 数据中心名称 |

---

## Storage Extended

### storage_get
获取存储域详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 存储域名称或 ID |

---

### storage_create
创建存储域

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 存储域名称 |
| `storage_type` | string | **是** | 存储类型（nfs/fc/iscsi等） |
| `host` | string | **是** | 主机名称 |
| `path` | string | **是** | 存储路径 |
| `datacenter` | string | 否 | 数据中心名称（可选） |
| `description` | string | 否 | 描述 |
| `domain_type` | string | 否 | 域类型（data/iso/export），默认 data |

---

### storage_delete
删除存储域

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 存储域名称或 ID |
| `force` | boolean | 否 | 强制删除，默认 false |

---

### storage_detach
分离存储域

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 存储域名称或 ID |
| `datacenter` | string | 否 | 数据中心名称（可选） |

---

### storage_attach_to_dc
附加存储域到数据中心

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 存储域名称或 ID |
| `datacenter` | string | **是** | 数据中心名称 |

---

### storage_stats
获取存储域统计信息

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 存储域名称或 ID |

---

### storage_refresh
刷新存储域

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 存储域名称或 ID |

---

### storage_update
更新存储域配置

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 存储域名称或 ID |
| `new_name` | string | 否 | 新名称 |
| `description` | string | 否 | 新描述 |
| `warning_low_space` | number | 否 | 低空间警告阈值（GB） |
| `critical_low_space` | number | 否 | 临界空间阈值（GB） |

---

### storage_files
列出存储域的文件

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 存储域名称或 ID |

---

### storage_connections_list
列出存储连接

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | 否 | 存储域名称或 ID（可选） |

---

### storage_available_disks
列出存储域上的可用磁盘

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 存储域名称或 ID |

---

### storage_export_vms
列出导出域上的 VM

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 导出域名称或 ID |

---

### storage_import_vm
从导出域导入 VM

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 导出域名称或 ID |
| `vm_name` | string | **是** | 要导入的 VM 名称 |
| `cluster` | string | **是** | 目标集群 |
| `storage_domain` | string | 否 | 目标存储域（可选） |
| `clone` | boolean | 否 | 是否克隆 |

---

## Disks Core

### disk_list
列出磁盘

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | 否 | VM 名称或 ID（可选） |
| `storage_domain` | string | 否 | 存储域名称（可选） |

---

### disk_create
创建磁盘

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 磁盘名称 |
| `size_gb` | number | **是** | 磁盘大小（GB） |
| `storage_domain` | string | 否 | 存储域名称 |
| `format` | string | 否 | 磁盘格式（cow/raw），默认 cow |

---

### disk_attach
附加磁盘

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `disk_id` | string | **是** | 磁盘 ID |

---

## Disks Extended

### disk_get
获取磁盘详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 磁盘名称或 ID |

---

### disk_delete
删除磁盘

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 磁盘名称或 ID |
| `force` | boolean | 否 | 强制删除，默认 false |

---

### disk_resize
调整磁盘大小

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 磁盘名称或 ID |
| `new_size_gb` | number | **是** | 新大小（GB） |

---

### disk_detach
从虚拟机分离磁盘

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 磁盘名称或 ID |
| `vm_name_or_id` | string | **是** | VM 名称或 ID |

---

### disk_move
移动磁盘到另一个存储域

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 磁盘名称或 ID |
| `target_storage_domain` | string | **是** | 目标存储域名称 |

---

### disk_stats
获取磁盘统计信息

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 磁盘名称或 ID |

---

### disk_update
更新磁盘配置

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 磁盘名称或 ID |
| `new_name` | string | 否 | 新名称 |
| `description` | string | 否 | 新描述 |
| `shareable` | boolean | 否 | 是否可共享 |
| `wipe_after_delete` | boolean | 否 | 删除后擦除 |

---

### disk_sparsify
精简磁盘（消除空白块）

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 磁盘名称或 ID |

---

### disk_export
导出磁盘到导出域

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 磁盘名称或 ID |
| `export_domain` | string | **是** | 导出域名称 |

---

### disk_snapshot_list
列出磁盘快照

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `disk_name_or_id` | string | **是** | 磁盘名称或 ID |

---

## Networks

### network_list
列出网络

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | 否 | 集群名称（可选） |

---

### network_get
获取网络详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 网络名称或 ID |

---

### network_create
创建网络

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 网络名称 |
| `cluster` | string | 否 | 集群名称（可选） |
| `datacenter` | string | 否 | 数据中心名称（可选） |
| `description` | string | 否 | 描述 |
| `mtu` | number | 否 | MTU 值 |

---

### network_update
更新网络

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 网络名称 |
| `new_name` | string | 否 | 新名称 |
| `description` | string | 否 | 新描述 |

---

### network_delete
删除网络

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 网络名称或 ID |

---

### nic_list
列出网卡

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### nic_add
添加网卡

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `nic_name` | string | **是** | 网卡名称 |
| `network` | string | **是** | 网络名称 |

---

### nic_remove
移除网卡

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `nic_name` | string | **是** | 网卡名称 |

---

## VNIC Profiles

### vnic_profile_list
列出 VNIC Profile

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `network` | string | 否 | 网络名称（可选） |

---

### vnic_profile_get
获取 VNIC Profile 详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | Profile 名称或 ID |

---

### vnic_profile_create
创建 VNIC Profile

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | Profile 名称 |
| `network` | string | **是** | 网络名称 |
| `description` | string | 否 | 描述 |
| `port_mirroring` | boolean | 否 | 是否启用端口镜像 |

---

### vnic_profile_update
更新 VNIC Profile

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | Profile 名称或 ID |
| `new_name` | string | 否 | 新名称 |
| `description` | string | 否 | 新描述 |
| `port_mirroring` | boolean | 否 | 端口镜像设置 |

---

### vnic_profile_delete
删除 VNIC Profile

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | Profile 名称或 ID |

---

## Network Filters & QoS

### network_filter_list
列出网络过滤器

**参数：**（无参数）

---

### mac_pool_list
列出 MAC 地址池

**参数：**（无参数）

---

### qos_list
列出 QoS 配置

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `datacenter` | string | 否 | 数据中心名称（可选） |

---

### iscsi_bond_list
列出 iSCSI Bond

**参数：**（无参数）

---

### template_disk_list
列出模板的磁盘

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 模板名称或 ID |

---

### template_nic_list
列出模板的网卡

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 模板名称或 ID |

---

### template_list
列出模板

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | 否 | 集群名称（可选） |

---

### template_vm_create
从模板创建 VM

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | VM 名称 |
| `template` | string | **是** | 模板名称 |
| `cluster` | string | **是** | 目标集群 |
| `memory_mb` | number | 否 | 内存（MB），可选 |
| `cpu_cores` | number | 否 | CPU 核数，可选 |

---

### template_get
获取模板详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 模板名称或 ID |

---

### template_create
从虚拟机创建模板

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 模板名称 |
| `vm` | string | **是** | 源虚拟机名称或 ID |
| `description` | string | 否 | 描述 |
| `cluster` | string | 否 | 目标集群（可选） |

---

### template_delete
删除模板

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 模板名称或 ID |
| `force` | boolean | 否 | 强制删除 |

---

### template_update
更新模板

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 模板名称或 ID |
| `new_name` | string | 否 | 新名称 |
| `description` | string | 否 | 新描述 |
| `memory_mb` | number | 否 | 内存（MB） |
| `cpu_cores` | number | 否 | CPU 核数 |
