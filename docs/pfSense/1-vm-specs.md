# VM Specifications

**Name**: pfSense
**VM ID**: 100 (infrastructure)
**CPU**: 2 cores
**RAM**: 2048 MB (2GB)
**DISK**: 20 GB
**Network Adapters**: 5

## Adapter Mapping:

net0 (vtnet0) -> vmbr0 (WAN/Internet)
net1 (vtnet1) -> vmbr1 (Corporate Network)
net2 (vtnet2) -> vmbr2 (Security Tools)
net3 (vtnet3) -> vmbr3 (DMZ)
net4 (vtnet4) -> vmbr4 (Red Team)
