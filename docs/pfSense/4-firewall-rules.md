# Firewall Rules

## Overview

Corporate (LAN) can access Security tools and internet
Security tools can access all networks (monitoring)
DMZ restricted (only web/DNS outbound)
Red Team completely isolated (controlled access)

### LAN Rules

**Allow LAN to SECURITY**
**Action:** Pass
**Interface:** LAN
**Address Family:** IPv4
**Protocol:** Any
**Source:** LAN net
**Destination:** SECURITY net
**Description:** Allow corporate to security tools

**Allow LAN to Internet**
**Action:** Pass
**Source:** LAN net
**Destination:** any
**Description:** Default allow LAN to any rule
*(This is a default rule that pfSense provides)*


## SECURITY Rules

**Allow SECURITY to Any**
**Action:** Pass
**Interface:** SECURITY
**Address Family:** IPv4
**Protocol:** Any
**Source:** SECURITY net
**Destination:** any
**Description:** Allow security tools to monitor all networks


## DMZ Rules

**Allow DMZ Limited Internet**
**Action:** Pass
**Interface:** DMZ
**Address Family:** IPv4
**Protocol:** TCP/UDP
**Source:** DMZ net
**Destination:** any
**Destination Port Range:** 
    From: HTTP (80)
    To: HTTP (80)
**Description:** Allow DMZ HTTP

**Allow DMZ Limited Internet (HTTPS)**
**Action:** Pass
**Interface:** DMZ
**Address Family:** IPv4
**Protocol:** TCP/UDP
**Source:** DMZ net
**Destination:** any
**Destination Port Range:**
    From: HTTPS (443)
    To: HTTPS (433)
**Description:** Allow DMZ HTTPS


**Allow DMZ DNS**
**Action:** Pass
**Interface:** DMZ
**Address Family:** IPv4
**Protocol:** UDP
**Source:** DMZ net
**Destination:** any
**Destination Port:** 53
**Description:** Allow DMZ DNS


## REDTEAM Rules

**Block All (explicit)**
**Action:** Block
**Interface:** REDTEAM
**Address Family:** IPv4
**Source:** REDTEAM net
**Destination:** any
**Description:** Block Red Team - Enable per scenario
**Log:** [check] *log packets that hare handled by this rule*

