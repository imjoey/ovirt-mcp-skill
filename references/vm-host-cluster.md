# 目录索引

| 分类 | 工具数 | 页码 |
|------|--------|------|
| [VM Core](#vm-core) | 9 | 2 |
| [VM Extended](#vm-extended) | 13 | 2 |
| [VM Pools](#vm-pools) | 5 | 3 |
| [VM Checkpoints](#vm-checkpoints) | 4 | 4 |
| [Snapshots](#snapshots) | 4 | 4 |
| [Hosts Core](#hosts-core) | 3 | 4 |
| [Hosts Extended](#hosts-extended) | 14 | 4 |
| [Clusters](#clusters) | 9 | 5 |
| [CPU Profiles](#cpu-profiles) | 2 | 6 |
| [Instance Types](#instance-types) | 2 | 6 |
| [DataCenter](#datacenter) | 5 | 6 |

---

## VM Core

### vm_list
列出虚拟机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | 否 | 集群名称（可选，用于过滤） |
| `status` | string | 否 | VM 状态过滤（up/down） |

---

### vm_get
获取虚拟机详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### vm_create
创建虚拟机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | VM 名称 |
| `cluster` | string | **是** | 目标集群 |
| `memory_mb` | number | 否 | 内存（MB），默认 4096 |
| `cpu_cores` | number | 否 | CPU 核数，默认 2 |
| `template` | string | 否 | 模板名称，默认 Blank |
| `disk_size_gb` | number | 否 | 磁盘大小（GB），默认 50 |
| `description` | string | 否 | VM 描述 |

---

### vm_start
启动虚拟机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### vm_stop
关闭虚拟机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `graceful` | boolean | 否 | 优雅关机，默认 true |

---

### vm_restart
重启虚拟机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### vm_delete
删除虚拟机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `force` | boolean | 否 | 强制删除，默认 false |

---

### vm_update_resources
更新 VM 资源

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `memory_mb` | number | 否 | 新内存（MB） |
| `cpu_cores` | number | 否 | 新 CPU 核数 |

---

### vm_stats
获取 VM 统计

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

## VM Extended

### vm_migrate
迁移虚拟机到另一台主机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `target_host` | string | 否 | 目标主机名称或 ID（可选） |

---

### vm_console
获取虚拟机控制台访问信息

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `console_type` | string | 否 | 控制台类型（spice/vnc），默认 spice |

---

### vm_cdrom_list
列出 VM 的 CDROM 设备

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### vm_cdrom_update
更新 VM 的 CDROM（挂载/弹出 ISO）

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `cdrom_id` | string | **是** | CDROM ID |
| `iso_file` | string | 否 | ISO 文件路径 |
| `eject` | boolean | 否 | 是否弹出光盘 |

---

### vm_hostdevice_list
列出 VM 的主机设备

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### vm_hostdevice_attach
将主机设备附加到 VM

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `device_name` | string | **是** | 设备名称 |

---

### vm_hostdevice_detach
从 VM 分离主机设备

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `device_name` | string | **是** | 设备名称 |

---

### vm_mediated_device_list
列出 VM 的介导设备（vGPU）

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### vm_numa_list
列出 VM 的 NUMA 节点

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### vm_watchdog_list
列出 VM 的 Watchdog 设备

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### vm_watchdog_update
更新 VM 的 Watchdog 配置

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `watchdog_id` | string | **是** | Watchdog ID |
| `action` | string | 否 | 触发动作（none/reset/poweroff/shutdown/dump） |

---

### vm_pin_to_host
将 VM 固定到指定主机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `host` | string | **是** | 主机名称或 ID |
| `pin_policy` | string | 否 | 固定策略（user/resizable/migratable） |

---

### vm_session_list
列出 VM 的活跃会话

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

## VM Pools

### vm_pool_list
列出虚拟机池

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | 否 | 集群名称（可选） |

---

### vm_pool_get
获取虚拟机池详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 池名称或 ID |

---

### vm_pool_create
创建虚拟机池

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 池名称 |
| `template` | string | **是** | 模板名称 |
| `cluster` | string | **是** | 集群名称 |
| `size` | number | 否 | 池大小，默认 5 |
| `description` | string | 否 | 描述 |
| `max_user_vms` | number | 否 | 每用户最大 VM 数，默认 1 |
| `prestarted_vms` | number | 否 | 预启动 VM 数，默认 0 |
| `stateful` | boolean | 否 | 是否有状态，默认 false |

---

### vm_pool_delete
删除虚拟机池

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 池名称或 ID |
| `force` | boolean | 否 | 强制删除 |

---

### vm_pool_update
更新虚拟机池

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 池名称或 ID |
| `new_name` | string | 否 | 新名称 |
| `size` | number | 否 | 新大小 |
| `description` | string | 否 | 新描述 |
| `prestarted_vms` | number | 否 | 预启动 VM 数 |

---

## VM Checkpoints

### vm_checkpoint_list
列出 VM 的检查点

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### vm_checkpoint_create
创建 VM 检查点

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `description` | string | 否 | 检查点描述 |

---

### vm_checkpoint_restore
恢复 VM 到检查点

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `checkpoint_id` | string | **是** | 检查点 ID |

---

### vm_checkpoint_delete
删除 VM 检查点

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `checkpoint_id` | string | **是** | 检查点 ID |

---

## Snapshots

### snapshot_list
列出快照

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |

---

### snapshot_create
创建快照

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `description` | string | 否 | 快照描述 |

---

### snapshot_restore
恢复快照

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `snapshot_id` | string | **是** | 快照 ID |

---

### snapshot_delete
删除快照

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | VM 名称或 ID |
| `snapshot_id` | string | **是** | 快照 ID |

---

## Hosts Core

### host_list
列出主机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | 否 | 集群名称（可选） |

---

### host_activate
激活主机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |

---

### host_deactivate
维护主机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |

---

## Hosts Extended

### host_get
获取主机详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |

---

### host_add
添加主机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 主机名称 |
| `cluster` | string | **是** | 集群名称 |
| `address` | string | **是** | 主机地址 |
| `password` | string | 否 | SSH 密码（可选） |
| `ssh_port` | number | 否 | SSH 端口，默认 22 |

---

### host_remove
移除主机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |
| `force` | boolean | 否 | 强制移除，默认 false |

---

### host_stats
获取主机统计信息

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |

---

### host_devices
获取主机设备列表

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |

---

### host_nic_list
列出主机网卡

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |

---

### host_nic_update
更新主机网卡配置

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |
| `nic_name` | string | **是** | 网卡名称 |
| `custom_properties` | object | 否 | 自定义属性 |

---

### host_numa_get
获取主机 NUMA 拓扑

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |

---

### host_hook_list
列出主机 Hook

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |

---

### host_fence
对主机执行 Fence 操作

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |
| `action` | string | **是** | 操作类型（restart/start/stop/status） |

---

### host_network_update
更新主机网络配置

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |
| `network` | string | **是** | 网络名称 |
| `nic` | string | 否 | 网卡名称（可选） |
| `vlan_id` | number | 否 | VLAN ID（可选） |
| `bond` | string | 否 | 绑定接口名称（可选） |

---

### host_device_update
更新主机设备配置

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |
| `device_name` | string | **是** | 设备名称 |
| `enabled` | boolean | 否 | 是否启用 |

---

### host_storage_list
列出主机存储

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |

---

### host_install
安装/重新安装主机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |
| `root_password` | string | 否 | root 密码 |
| `ssh_key` | string | 否 | SSH 公钥 |
| `override_iptables` | boolean | 否 | 覆盖 iptables 规则 |

---

### host_iscsi_discover
发现 iSCSI 目标

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |
| `address` | string | **是** | iSCSI 目标地址 |
| `port` | number | 否 | 端口号，默认 3260 |
| `username` | string | 否 | CHAP 用户名（可选） |
| `password` | string | 否 | CHAP 密码（可选） |

---

### host_iscsi_login
登录到 iSCSI 目标

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 主机名称或 ID |
| `address` | string | **是** | iSCSI 目标地址 |
| `target` | string | **是** | 目标名称 |
| `port` | number | 否 | 端口号，默认 3260 |
| `username` | string | 否 | CHAP 用户名（可选） |
| `password` | string | 否 | CHAP 密码（可选） |

---

## Clusters

### cluster_list
列出集群

**参数：**（无参数）

---

### cluster_get
获取集群详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 集群名称 |

---

### cluster_create
创建集群

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 集群名称 |
| `datacenter` | string | **是** | 数据中心名称 |
| `cpu_type` | string | **是** | CPU 类型 |
| `description` | string | 否 | 描述 |
| `gluster_service` | boolean | 否 | 是否启用 Gluster 服务 |
| `threads_per_core` | number | 否 | 每核心线程数 |

---

### cluster_update
更新集群

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 集群名称或 ID |
| `new_name` | string | 否 | 新名称 |
| `description` | string | 否 | 新描述 |
| `threads_per_core` | number | 否 | 每核心线程数 |

---

### cluster_delete
删除集群

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 集群名称或 ID |

---

### cluster_hosts
集群主机

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 集群名称 |

---

### cluster_vms
集群 VM

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 集群名称 |
| `status` | string | 否 | VM 状态过滤（可选） |

---

### cluster_cpu_load
集群 CPU 负载

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 集群名称 |

---

### cluster_memory_usage
集群内存使用

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 集群名称 |

---

## CPU Profiles

### cpu_profile_list
列出 CPU Profile

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | **是** | 集群名称或 ID |

---

### cpu_profile_get
获取 CPU Profile 详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `cluster` | string | **是** | 集群名称或 ID |
| `name_or_id` | string | **是** | Profile 名称或 ID |

---

## Instance Types

### instance_type_list
列出实例类型

**参数：**（无参数）

---

### instance_type_get
获取实例类型详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 实例类型名称或 ID |

---

## DataCenter

### datacenter_list
列出数据中心

**参数：**（无参数）

---

### datacenter_get
获取数据中心详情

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 数据中心名称或 ID |

---

### datacenter_create
创建数据中心

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name` | string | **是** | 数据中心名称 |
| `storage_type` | string | 否 | 存储类型（nfs/fc/iscsi等），默认 nfs |
| `description` | string | 否 | 描述 |

---

### datacenter_update
更新数据中心

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 数据中心名称或 ID |
| `new_name` | string | 否 | 新名称（可选） |
| `description` | string | 否 | 新描述（可选） |

---

### datacenter_delete
删除数据中心

**参数：**
| 参数 | 类型 | 必填 | 描述 |
|------|------|------|------|
| `name_or_id` | string | **是** | 数据中心名称或 ID |
