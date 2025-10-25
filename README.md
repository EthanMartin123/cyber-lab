# Cyber-Lab & Cybersecurity Research 

A professional-grade cybersecurity detection and response lab that mirrors enterprise security operations.

## 🎯 Project Goals

This lab will include:
 - Virtual machines across 5 network segments
 - 15+ industry-standard security tools 
 - Detection rules mapped to MITRE ATT&CK framework
 - Automated incident and response workflows
 - Documented attack and defense scenarios

## 🔒 Tech Stack 

 - Proxmox for virtualization and network segments
 - Splunk as a SIEM 
 - Wazuh for EDR 
 - Zeek/Suricata for network monitoring
 - MISP for threat intelligence
 - TheHive for incident response 
 - Shuffle for SOAR 

### 🚧 Network Segments 

 1. Management Network (vmbr0)
    Purpose: Proxmox administration and internet access 

 2. Coporate Network (vmbr1)
    Purpose: "Production" environment with Active Directory 
    Contains: Domain controllers, workstations, file servers
 
 3. Security Tools Network (vmbr2)
    Purpose: SIEM, monitoring, and security infrastructure
    Contains: Splunk, Wazuh, TheHive, MISP 

 4. DMZ (vmbr3)
    Purpose: Vulnerable applications and exposed services 
    Contains: Metasploitable, DVWA, web applications 

 5. Red Team Network (vmbr4)
    Purpose: Isolated attacked infrastructure 
    Contains: Kali Linux, attack tools, C2 servers 

## 📚 What I Aim To Learn 

### 🛠️ Technical Skills
 - Configure enterprise security tools from scratch 
 - Write detection rules (Sigma format, SPL, YARA)
 - Analyze logs and network traffic for threats 
 - Conduct digital forensics investigations 
 - Automate security workflows with Python 
 - Better understand common attack techniques and how to detect them

### 📝 Analytical Skills 
 - Threat hunting methodology and process 
 - Incident investigation procedures
 - Root cause analysis of security events 
 - Risk assessment and prioritization
 - Pattern recognition in security data

### 🤝 Soft Skills 
 - Technical documentation and report writing 
 - Communication of technical concepts 


## 🎓 More About Me 

This is part of my cybersecurity portfolio as I work toward an entry-level SOC analyst position. I'm building hands-on projects to demonstrate real-world security skills.

**Author:** Ethan Martin  
**University:** California State University, Channel Islands  
**Major:** Information Technology  
**Club:** Treasurer, Ethical Hackers of Channel Islands

--- 

This is a personal learning project, but feedback and suggestions are welcome!

⭐ **Star this repo if you find it useful or interesting!**

