**Hostname:** Firewall
**Domain:** cyberlab.local

**Primary DNS Server:** 8.8.8.8 (google)
**Secondary DNS Server:** 1.1.1.1 (cloudflare)
*(These are used by pfSense to resolve domain names & are passed to DHCP clients)*

**Override DNS:** [unchecked]
*(Allows for DHCP clients to use their own DNS if configured and gives more flexibility)*

**Time server hostname:** pool.ntp.org
*(This keeps the clocks synchronized)*

**Timezone:** PST

**WAN IP:** 192.168.1.11/24
**Gateway:** 192.168.1.1
*(These were configured via console)*

**Block RFC1918 Private Networks:** [unchecked]
*(WAN is already on private network, this would block necessary traffic)*

**Block bogon networks:** [checked]
*(blocks incoming traffic from illegitimate IP addresses)*

**LAN IP**: 10.0.10.1/24
**Subnet Mask:** 24
*(Again, configured via console)*

**Admin Password** [strong password]
**Confirm:** [repeat password]

**Reload & Finish!**
