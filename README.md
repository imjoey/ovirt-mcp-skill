# ovirt-mcp

[OpenClaw](https://github.com/openclaw/openclaw) Agent Skill for [oVirt MCP Server](https://github.com/imjoey/ovirt-engine-mcp-server) — comprehensive reference documentation for 186 oVirt/RHV infrastructure management tools.

## What is this?

This skill helps AI agents (Claude, GPT, etc.) understand and use the oVirt MCP Server's full toolset. It provides:

- **Quick Start** — install and configure the MCP server in under a minute
- **Tool Reference** — all 186 tools organized by domain with parameter schemas
- **Error Handling** — error codes, retry strategies, and troubleshooting
- **Common Workflows** — ready-to-use patterns for frequent operations

## Structure

```
ovirt-mcp/
├── SKILL.md                              # Entry point: quick start, architecture, tool index
└── references/
    ├── vm.md              (35 tools)      # VM lifecycle, pools, checkpoints, snapshots
    ├── host.md            (19 tools)      # Host management, fencing, iSCSI
    ├── cluster.md         (11 tools)      # Clusters, CPU profiles
    ├── datacenter.md       (5 tools)      # Data centers
    ├── instance-types.md   (2 tools)      # Instance types
    ├── storage.md         (16 tools)      # Storage domains, connections, iSCSI bonds
    ├── disk.md            (13 tools)      # Disk lifecycle, snapshots, move, resize
    ├── network.md         (16 tools)      # Networks, VNIC profiles, QoS, MAC pools
    ├── template.md         (8 tools)      # Template lifecycle, disk/NIC lists
    ├── system.md           (6 tools)      # System info, jobs
    ├── events.md          (11 tools)      # Events, bookmarks, alerts
    ├── rbac.md            (24 tools)      # Users, groups, roles, permissions, tags
    ├── quota.md            (7 tools)      # Data center quotas
    └── affinity.md        (13 tools)      # Affinity groups and labels
```

## Install

### Via ClawHub

```bash
clawhub install ovirt-mcp
```

### From Source

```bash
git clone https://github.com/imjoey/ovirt-mcp-skill.git
cp -r ovirt-mcp-skill ~/.openclaw/skills/
```

## Prerequisites

- [oVirt MCP Server](https://github.com/imjoey/ovirt-engine-mcp-server) installed and configured
- oVirt Engine 4.4+
- Python >= 3.10

## Tool Coverage

| Domain | Tools | Examples |
|--------|-------|---------|
| Virtual Machines | 35 | `vm_create`, `vm_start`, `vm_migrate`, `vm_console` |
| Hosts | 19 | `host_add`, `host_fence`, `host_install` |
| Clusters | 11 | `cluster_create`, `cluster_cpu_load` |
| Networks | 16 | `network_create`, `vnic_profile_*` |
| Storage | 16 | `storage_create`, `storage_import_vm` |
| Disks | 13 | `disk_create`, `disk_resize`, `disk_move` |
| RBAC | 24 | `user_create`, `permission_assign`, `role_*` |
| Events | 11 | `event_search`, `event_alerts` |
| Templates | 8 | `template_vm_create`, `template_disk_list` |
| Other | 33 | Affinity, quotas, system, datacenter, instance types |
| **Total** | **186** | |

## Related Projects

- [oVirt MCP Server](https://github.com/imjoey/ovirt-engine-mcp-server) — The MCP server this skill documents
- [oVirt](https://www.ovirt.org/) — Open-source virtualization management
- [ovirtsdk4](https://github.com/oVirt/ovirt-engine-sdk-python) — Official oVirt Python SDK
- [Model Context Protocol](https://modelcontextprotocol.io/) — The MCP specification

## License

MIT
