### Applied Incident Response

**Author:** Steve Anson 
**Status:** Reading  
**Started:** 11/15/25  
**Finished:** TBD   
**Rating:** TBD 

## Why I'm Reading This
To learn and apply incident response best practices within my cybersecurity home lab

## Key Takeaways
To succeed in Cybersecurity you need:
 - Good IT housekeeping
 - To know what "normal" looks like in your network 
 - An understanding of attacker's motivations
 - Expertise with a variety of tools (Firewalls, SIEMs, EDR)
 - Good telemetry (Failing to collect adequate telemetry (logs, network packet captures, and other records of events that occur throughout the network) in advance of an incident is an easy way to lose the war before the first battle begins.)
 - An understanding of how an attack is conducted (Cyber Kill Chain, MITRE ATT&CK Framework) 
 - Ability to use deception techniques 

## Chapter Notes

### Chapter 1: The Threat Landscape

# Cybersecurity Attack Motivations and Methods

## Common Attacker Motivations

Broadly speaking, the most common motivations for an attacker are:
- Intelligence (espionage)
- Financial Gain
- Disruption

### Detailed Motivations

**Intellectual Property Theft**  
The stealing of secret recipes, proprietary technologies, or any other knowledge that provides an advantage to the organization.

**Supply Chain Attack**  
Attacking the supply chain of the ultimate target rather than attacking the target system head on.

**Financial Fraud**  
Theft of credit card information, phishing of online banking credentials, and compromise of banking systems.

**Extortion**  
Any information that can be harmful or embarrassing to a potential victim is used to extort money from victims.

**Espionage**  
Information targeted that is intellectual property or broader types of information, which can provide a competitive or strategic advantage to the attacker.

**Power**  
The ability to leverage cyber power in conjunction with kinetic or physical warfare.

**Hacktivism**  
Using attacks on information systems as a means of protest, similar to marches or sit-ins.

**Revenge**  
Retribution through cyberattacks. Disgruntled employees, former employees, dissatisfied customers, citizens of another nation, or former acquaintances are candidates for these types of cyberattacks.

## Attack Methods

### DoS and DDoS

An attack that seeks to make a service unavailable for its intended purpose. Examples include malformed packet exploits or the exhaustion of network bandwidth. If all the bandwidth is consumed with nonsense traffic, legitimate traffic is unable to reach the service.

Attacks can come across multiple systems all attacking a single victim and are therefore called distributed denial-of-service (DDoS) attacks.

**Amplification Attack** - Amplifying the attacker's bandwidth by bouncing it off a server that will respond with a larger payload than was sent.

DDoS attacks rely on the fact that they are able to send more data than the victim's ISP is able to support. There isn't much a victim can do to mitigate these kinds of attacks within their network.

**Solutions:**
- Edge router or firewall configured to block incoming floods, but ISP would still be saturated and legitimate traffic can't come through
- Mitigation of DoS attacks are provided by ISPs or dedicated anti-DDoS provider

**Further Reading:**
- [Github Survived the Biggest DDoS Attack Ever Recorded](https://www.wired.com/story/github-ddos-memcached/)
- [Memcached DDoS Attack](https://www.cloudflare.com/learning/ddos/memcached-ddos-attack/)

### Worms

A general class of malware that can self-replicate.

**Examples include:**
- [LoveBug](https://en.wikipedia.org/wiki/ILOVEYOU)
- [Code Red](https://en.wikipedia.org/wiki/Code_Red_(computer_worm))
- [SQL Slammer](https://en.wikipedia.org/wiki/SQL_Slammer)
- [WannaCry](https://en.wikipedia.org/wiki/WannaCry_ransomware_attack)

**General overview on how worms work:**
1. Scan a system susceptible to a specific vulnerability
2. Exploit the vulnerable system
3. Replicate their code to that system
4. Begin scanning anew for other victims to infect

Detection of worms is generally not difficult; large-scale attacks prompt global IT awareness.

### Ransomware

A class of malware that encrypts victim's data with a key known only to the attacker. To receive that key, victims are asked to pay a fee to the ransomware authors.

IT security practitioners advise against paying a ransom.

**Examples:**
- [CryptoLocker](https://en.wikipedia.org/wiki/CryptoLocker)
- [GandCrab](https://www.knowbe4.com/ransomware-knowledgebase/gandcrab)

### Phishing

Emails claiming to be from organizations trusted by the victim request that the victim click a link, download an attachment, or provide authentication credentials.

**Spear Phishing**  
Targeted attacks against high-value individuals that include phishing techniques.

**Watering Hole Attacks**  
Directs victims to a website that will deliver a malicious payload to anyone who visits.

### Web Attacks

Attacks against a service that rely on HTTP:
- Direct exploitation of servers
- Cross-site scripting
- Cross-site request forgeries
- Logic attacks against applications
- Attacks against vulnerabilities in APIs

### Wireless Attacks

Attacks against technologies such as Wi-Fi, Bluetooth, and even GSM.

WPA3 provides the best protections for many wireless networks (vulnerabilities already being identified). WPA2 offers reasonable levels of protection when properly implemented.

**GSM are subject to attacks from:**
- Signaling System No. 7 (SS7) signaling vulnerabilities
- International mobile subscriber identity (IMSI) catchers
- Subscriber Identity module (SIM) card attacks

Access to public Wi-Fi networks is a common vector for attackers to gain a foothold on a client system.

**Example:** [DarkHotel Campaign](https://en.wikipedia.org/wiki/DarkHotel)

VPN mitigates the risk associated with this type of attack.

### Sniffing and MitM

Attackers who are able to insert their system into the stream of communication are able to intercept or modify the data in transit.

The modification of ARP cache tables can be used to redirect traffic from its intended destination to the attacker system.

### Crypto Mining

Delivery of software to mine for cryptocurrencies, providing any associated gains to the attacker's account. Often favor the Monero cryptocurrency.

Victims experience an increase in processor utilization and associated electricity costs.

This kind of malware tends to be stealthy.

### Password Attacks

**Brute force password guessing** - Trying large number of possible passwords for an account

**Password spraying** - Guessing a small number of passwords against a large number of users to reduce the chance of account lockout

Many organizations still store passwords using weak hashes (MD5), and sometimes in plain text.

NIST has advised the use of passphrases, a combination of random words to provide a longer passphrase that is harder to guess but simple for a person to remember.

**For aligning identity management best practices:**  
[NIST Special Publication 800-63C](https://pages.nist.gov/800-63-3/sp800-63c.html)

## Anatomy of an Attack

### Attacker Methodology Models

- [Lockheed Martin Cyber Kill Chain](https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html)
- [Unified Kill Chain by Paul Pols](https://www.unifiedkillchain.com/assets/The-Unified-Kill-Chain.pdf)
- [MITRE ATT&CK](https://attack.mitre.org/)

### Attack Phases

**Reconnaissance**  
The conducting of open-source intelligence to determine as much about the target as possible.
- Passive - Without scans and touching the network
- Active - Network scans

**Exploitation**  
Taking advantage of a vulnerability(s) to gain an initial foothold within the target organization.

**Expansion/Entrenchment**  
"Active battleground between attackers and defenders"  
"Live off the land" - Seeking to use only software that is already present within the victim network.

**Exfiltration/Damage**  
Execution of data extraction, defacement, or whatever the attacker had originally planned.

**Clean Up**  
Attacker cleans up evidence.

## The Modern Adversary

Publicly available exploits or malware will almost certainly result in detection. To remain stealthy, attackers obtain valid credentials and reuse those credentials to access new systems.

Once a foothold is gained, attackers will pillage systems for additional intelligence.

ARP cache, checking log entries, using network browsing activity, and target scans are common techniques to find additional information and credentials.

### Chapter 2: Incident Readiness

**Cyber Resiliency** is the ability to anticipate, withstand, recover from, and adapt to adverse conditions, stress, attacks, or compromises on systems taht include cyber resources.

[Developing Cyber Resilient Systems: A Systems Security Engineering Approach](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-160v2r1.pdf)

Incident response is one component of a larger, active defense process.

[The Sliding Scale of Cyber Security](https://www.sans.org/white-papers/36240)

To be effective...

**IR must coordinate with security monitoring team as well as operations teams that control the network environment**
**Good IT housekeeping including understanding the assets that comprise the network**
**Security monitoring operations detecting potential threats and escalating them for further incident response**
**IR must identify scope of the incident and develop a plan to remediate the impact of the advesary**
**This plan should be communicated and coordinated with the various teams to contain, eradicate, and recover from the adversary action**
**Threat Intelligence used to improve the preventive and detective controls throughout the network**

[Incident Response Recommendations and Considerations for Cybersecurity Risk Management](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r3.pdf)

"Systems themselves cannot provide an active defense; systems can only server as tools to teh active defender ... What makese advanced threats persistent
and dangerous is the adaptive and intelligent adversary behind the keyboard. Countering these adversaries requires equally flexible and intelligent defenders" - Robert M. Lee

**Request Tracker for Incident Response (RTIR)** - used to track various categories of information, storing artifacts, tracking request tickets, facilitating information sharing and communication, and more.
[More information on RTIR](https://requesttracker.com/rtir/)
[Fast Incident Response (FIR)](https://github.com/certsocietegenerale/FIR)
[The Hive](https://strangebee.com/)

## Preparing Your Technology

Failing to collect adequate telemetry (logs, network packet captures, and other records of events that occur throughout the network) in advance of an incident is an easy way to lose the war before the first battle begins. 

In order to identify the abnormal, you must have a clear understanding of what normal looks like. 

**Basic IT Housekeeping should include...**
 - understand the processes, services, and ports in use
 - have accurate and up-to-date IT asset inventory
 - maintaining an organized system for change management, including updates and patches
 - have accurate network diagrams

"There is no such thing as advanced defense, only flawless execution of the basics."

**Network Segmentation can be done on...**
 - Layer 3 using subnets, including security mechanisms provided by firewalls or other security screening devices
 - Layer 2 using VLANs on switches

**ZERO-TRUST NETWORKS**
 - The use of microsegmentation, application-aware firewalls, least-privilege access, and other related
   technologies to constrain user activity and prevent lateral movement by an advesary.


**Threat Intelligence** is processed informaiton regarding threat actors, malicious tools, adversary techniques,
and other details that may impact the threats faced by your organization and their accompanying risks. 

### Ensuring Adequate Visibility

**Compliance SIEM** collects and stores all data from the network. This leads to long query times and a lot of time
to produce a result.

**Tactical SIEM** collects high-value security event records and is used for incident response procedures. 

[Spotting the Adversary with Windows Event Log Monitoring(Revision 2)](https://massarobi.wordpress.com/wp-content/uploads/2017/03/spotting-the-adversary-with-windows-event-log-monitoring.pdf)

[Malware Archaeology Windows Log Cheat Sheet](https://www.malwarearchaeology.com/cheat-sheets)

**Important Log Sources for a tactical SIEM**

DNS Logs
    Attackers use C2 infrastructure to interact with victim networks, send commands, receive stolen information, update malware, and managed hijacked systems. DNS is a primse source of information about attacker activity for defenders.
    DNS logs can proactively monitor for known-malicious domains or hosts and generate an alert when a match is found.

HTTP/HTTPs Logs
    These logs should be monitored to alert:
        known bad URLs
        unusual user agents
        abnormaly long URLs
        communicationt to known bad domains
        recurring beacons
        abnormally large numbers of connections
        large amount of data being transmitted outbound
        unusual encoding
        any other potential indicators

System Logs
    These logs shuould be monitored to alert:
        successful and failed authenticaation attempts
        access to specific services such as web logs
        access to important files
        modifications to the kernel such as the loading of kernel modules
        any other potential indicators

Endpoint Detection Logs
    These can consist of endpoint detection and response technologies or antivirus products and should be sent to a tactical SIEM

Network boundarie/Segment boundarie Logs
    NetFlow or IPFIX can create log data by observing network traffic as it passes. 
    
    A flow consists of a source IP address, a source port (if applicable), a destination IP address, a destination port (if applicable), and the IP type of service being used to facilitate the network communication.

    If an attacker IP address has been identified, you can quickly query flow data to identify which systems in the network have interaceted with the malicious IP.
    If an attacker is laterally moving within the network over a specific port, flow data can help identify suspicious activity and other compromised hosts
    If data exfiltration is suspected, flow data can identify systems that have had unusually large outbound transmissions and IP address to which the data was sent. 

Firewall Logs
    These can show:
        connections that were dropped
        ids/ips system logs showing signature matches
        antimalware logs
        data loss prevention systems
        other network security devices

    Network Security Monitoring refers to monitoring of communications on the wire for security-related events. A prime example of this being Zeek.

### Deception Techniques

A honeypot is a system in an environemtn that entices attackers but have no legitimate business purpose. These are used to reveal attackers within a network. 
This concept can be extended to user accounts, file, and hashes in memory. These types of decoy items are often referred to as canaries.

[Cowries | fake SSH service]((https://github.com/cowrie/cowrie)
[WebLabryinth | fake website]((https://github.com/mayhemiclabs/weblabyrinth)


[Modern Honey Network (MHN)](https://github.com/threatstream/mhn) is an easy way to deploy several different honeypot technologies.

A decoy domain account can be created for the sole purpose of detecting malicious activity. 
 - use a very long, randomized password

A honey hash is a credential that is inserted into the memroy of a running system. It should not impact the system or ever reveal its presence, unless an attacker uses a tool like Mimikatz to steal credentails adn resuse them within
the environment. To ensure the account cannot be used by an attacker, you canplant it in memory with a password hash that does not represent the account's actual password using tools like the New-HoneyHash.ps1 script: https://github.com/EmpireProject/Empire/blob/master/data/module_source/management/New-HoneyHash.ps1

**To create honey hashes...**
1. createa  privileged honey account that you will never use in production, such as a member of the Domain Administrators group
2. Congiure with a long, randomized password to prevent any realistic exposure from password guessing.
3. Configure SIEM to alert on any attempts to log on with this account
4. Plant honey hashes on system using [New-HoneyHash.ps1](https://github.com/EmpireProject/Empire/blob/master/data/module_source/management/New-HoneyHash.ps1)
5. Script takes domain, account name, and account password parameters
6. Credentails are then stored in the memory of the Local Security Authority Subsystem Service (LSASS) process

When attackers try and use these credentials with the incorrect password placed into memory, their login attempts can force an alert of a failed logon attempt for a decoy account. 

It's possible to use startup scripts, which will push out through group policy, to place honey hashes on multiple systems throughout the environment. 

It's possible to place files that have no legitmate business purpose on production servers and configure the files with detailed auditing to alert on any interaction. Names of files should look enticing to attackers.

[More information on Canary Tokens](https://canarytokens.org)


## Applied to My Lab
- Implemented X based on Chapter 5
- Created detection rule inspired by page 142
- [Link to relevant scenario or config]

## Resources Mentioned
- Tools recommended in the book
- Links to additional reading
