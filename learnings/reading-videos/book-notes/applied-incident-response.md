# Applied Incident Response

**Author:** Steve Anson 
**Status:** Reading  
**Started:** 11/15/25  
**Finished:** TBD   
**Rating:** TBD 

## Why I'm Reading This
To learn and apply incident response best practices within my cybersecurity home lab

## Key Takeaways

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
...

## Applied to My Lab
- Implemented X based on Chapter 5
- Created detection rule inspired by page 142
- [Link to relevant scenario or config]

## Resources Mentioned
- Tools recommended in the book
- Links to additional reading
