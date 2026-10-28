# secbyte-active-directory-kerberos-lateral-movement-ctf-labs
A practical collection of cybersecurity CTF labs covering Active Directory attack path mapping (BloodHound), Kerberos abuse (AS-REP Roasting, Kerberoasting, Golden/Silver Tickets, Overpass-the-Hash, Pass-the-Ticket), Pass-the-Hash, WMI abuse, and Living off the Land (LOLBins).
# Active Directory Attack Paths, Kerberos Attacks & Lateral Movement CTF Labs

Welcome to the **Active Directory Attack Paths, Kerberos Attacks & Lateral Movement CTF Lab Collection**. This repository serves as an organized, searchable catalog of practical cybersecurity labs hosted on Learn SecByte.

This collection focuses on advanced Active Directory post-exploitation, identity compromise, and internal network propagation—including **Domain Graph Attack Path Mapping (BloodHound)**, **Kerberos Ticket Abuse (AS-REP Roasting, Kerberoasting, Golden/Silver Tickets, Pass-the-Ticket)**, **Credential Reuse (Pass-the-Hash, Overpass-the-Hash)**, and **Living off the Land (WMI, LOLBins, PowerShell)**.

---

## Lab Collection Index

### 1. Active Directory Attack Path Discovery
* **BloodHound Fundamentals: Mapping Active Directory Attack Path**  
  *Lab Link:* [https://learn.secbyte.org/ctf/bloodhound-fundamentals-mapping-active-directory-attack-path](https://learn.secbyte.org/ctf/bloodhound-fundamentals-mapping-active-directory-attack-path)  
  *Focus:* Collecting domain graph telemetry using SharpHound/BloodHound.py, querying Cypher graph relationships, identifying high-value targets, and discovering hidden privilege escalation paths to Domain Admin.

<Image src="image_agent_tag_3473752816752110808" alt="BloodHound Active Directory attack path graph showing node relationships and privilege escalation vectors" caption="BloodHound AD Attack Path Graph Mapping" />

---

### 2. Kerberos Protocol Exploitation & Ticket Forgery
* **AS-REP Roasting: Kerberos Without Pre-Authentication**  
  *Lab Link:* [https://learn.secbyte.org/ctf/as-rep-roasting-kerberos-without-pre-authentication](https://learn.secbyte.org/ctf/as-rep-roasting-kerberos-without-pre-authentication)  
  *Focus:* Identifying domain user accounts configured with `DONT_REQ_PREAUTH`, requesting encrypted AS-REP response blobs without credentials, and cracking hashes offline with Hashcat/John the Ripper.

* **Kerberoasting: The Roast of the Realm**  
  *Lab Link:* [https://learn.secbyte.org/ctf/kerberoasting-the-roast-of-the-realm](https://learn.secbyte.org/ctf/kerberoasting-the-roast-of-the-realm)  
  *Focus:* Enumerating Service Principal Names (SPNs), requesting TGS service tickets for target services, extracting Kerberos tickets from memory, and cracking TGS hashes to reveal cleartext passwords.

* **Silver Ticket Attack: Forged Access in Kerberos**  
  *Lab Link:* [https://learn.secbyte.org/ctf/silver-ticket-attack-forged-access-in-kerberos](https://learn.secbyte.org/ctf/silver-ticket-attack-forged-access-in-kerberos)  
  *Focus:* Forging Kerberos Service Tickets (TGS) using compromised service account NTLM hashes, bypassing the Key Distribution Center (KDC), and gaining persistence on target host services (MSSQL, CIFS, HTTP).

* **Golden Ticket Forgery: Kerberos Domain Compromise**  
  *Lab Link:* [https://learn.secbyte.org/ctf/golden-ticket-forgery-kerberos-domain-compromise](https://learn.secbyte.org/ctf/golden-ticket-forgery-kerberos-domain-compromise)  
  *Focus:* Extracting the domain `krbtgt` account hash, forging Ticket Granting Tickets (TGT) with custom lifetime parameters and Domain Admin SID rights, and establishing complete domain dominance.

<Image src="image_agent_tag_3473752816752110081" alt="Diagram illustrating the basic Kerberos authentication exchange between Client, KDC, and Service" caption="Kerberos Authentication & TGT Exchange Flow" />

---

### 3. Identity Abuse & Credential Reuse
* **Overpass-the-Hash: Kerberos Credential Abuse**  
  *Lab Link:* [https://learn.secbyte.org/ctf/overpass-the-hash-kerberos-credential-abuse](https://learn.secbyte.org/ctf/overpass-the-hash-kerberos-credential-abuse)  
  *Focus:* Leveraging user NTLM or AES hashes to request valid Kerberos TGTs directly from the KDC (Pass-the-Key), transforming hash-based access into full Kerberos ticket authentication.

* **Pass-the-Ticket: Kerberos Abuse Lab**  
  *Lab Link:* [https://learn.secbyte.org/ctf/pass-the-ticket-kerberos-abuse-lab](https://learn.secbyte.org/ctf/pass-the-ticket-kerberos-abuse-lab)  
  *Focus:* Harvesting active Kerberos tickets (TGT/TGS) from LSASS memory using Mimikatz or Rubeus, injecting cached `.kirbi` tickets into secondary sessions, and accessing restricted domain resources.

* **Pass-the-Hash: NorthStar Finance Incident**  
  *Lab Link:* [https://learn.secbyte.org/ctf/pass-the-hash-northstar-finance-incident](https://learn.secbyte.org/ctf/pass-the-hash-northstar-finance-incident)  
  *Focus:* Investigating or executing Pass-the-Hash (PtH) techniques using captured NTLM hashes via `psexec.py`, `wmiexec.py`, or `evil-winrm` across internal corporate workstations.

### 4. Lateral Movement & Living off the Land (LOLBins)
* **Lateral Movement Basics: Inside the Flat Network**  
  *Lab Link:* [https://learn.secbyte.org/ctf/lateral-movement-basics-inside-the-flat-network](https://learn.secbyte.org/ctf/lateral-movement-basics-inside-the-flat-network)  
  *Focus:* Exploring internal propagation techniques across unsegmented networks, remote service creation, Scheduled Tasks (`schtasks`), and admin share access (`C$`, `ADMIN$`).

* **WMI Abuse: Living Off The Land**  
  *Lab Link:* [https://learn.secbyte.org/ctf/wmi-abuse-living-off-the-land](https://learn.secbyte.org/ctf/wmi-abuse-living-off-the-land)  
  *Focus:* Executing remote commands via Windows Management Instrumentation (WMI), creating stealthy WMI event subscriptions for host persistence, and querying remote WMI classes.

* **PowerShell Attacks: Script Blocks & LOLBin Defense**  
  *Lab Link:* [https://learn.secbyte.org/ctf/powershell-attacks-script-blocks-lolbin-defense](https://learn.secbyte.org/ctf/powershell-attacks-script-blocks-lolbin-defense)  
  *Focus:* Analyzing malicious PowerShell script blocks, bypass techniques for constrained language mode (CLM), in-memory execution, and auditing Script Block Logging telemetry.

* **Living Off The Land: Windows Tradecraft Lab**  
  *Lab Link:* [https://learn.secbyte.org/ctf/living-off-the-land-windows-tradecraft-lab](https://learn.secbyte.org/ctf/living-off-the-land-windows-tradecraft-lab)  
  *Focus:* Executing advanced offensive tradecraft using native Windows binaries (LOLBins) to perform file downloads, process execution, and privilege escalation without dropping third-party tooling.

---

## Learning Path

### Path A: Active Directory & Kerberos Exploitation Specialist
1. **Attack Path Recon:** Start with [BloodHound Fundamentals](https://learn.secbyte.org/ctf/bloodhound-fundamentals-mapping-active-directory-attack-path).
2. **Roasting & Hash Harvesting:** Execute credential harvesting via [AS-REP Roasting](https://learn.secbyte.org/ctf/as-rep-roasting-kerberos-without-pre-authentication) and [Kerberoasting](https://learn.secbyte.org/ctf/kerberoasting-the-roast-of-the-realm).
3. **Ticket Forgery & Dominance:** Forge Kerberos access via [Silver Ticket Attack](https://learn.secbyte.org/ctf/silver-ticket-attack-forged-access-in-kerberos) and [Golden Ticket Forgery](https://learn.secbyte.org/ctf/golden-ticket-forgery-kerberos-domain-compromise).

### Path B: Lateral Movement & Post-Exploitation Operator
1. **Ticket & Hash Reuse:** Master authentication reuse via [Overpass-the-Hash](https://learn.secbyte.org/ctf/overpass-the-hash-kerberos-credential-abuse), [Pass-the-Ticket](https://learn.secbyte.org/ctf/pass-the-ticket-kerberos-abuse-lab), and [Pass-the-Hash: NorthStar Finance Incident](https://learn.secbyte.org/ctf/pass-the-hash-northstar-finance-incident).
2. **Internal Movement & LOLBins:** Propagate through networks using [Lateral Movement Basics](https://learn.secbyte.org/ctf/lateral-movement-basics-inside-the-flat-network), [WMI Abuse](https://learn.secbyte.org/ctf/wmi-abuse-living-off-the-land), [PowerShell Attacks](https://learn.secbyte.org/ctf/powershell-attacks-script-blocks-lolbin-defense), and [Living Off The Land: Windows Tradecraft Lab](https://learn.secbyte.org/ctf/living-off-the-land-windows-tradecraft-lab).

---

## How to Use the Labs

1. Select a practice scenario from the **Lab Collection Index**.
2. Click the direct link to launch the exercise environment on Learn SecByte.
3. Review scenario directives, domain targets, user lists, and network topologies.
4. Run BloodHound collectors, roast service accounts for hashes, forge Golden/Silver Kerberos tickets, or execute WMI/LOLBin commands to capture flags.

---

## Target Audience

* **Red Team Operators & Ethical Hackers:** Map domain attack graphs, exploit Kerberos ticket weaknesses, and execute living-off-the-land tradecraft.
* **Penetration Testers:** Perform post-exploitation lateral movement across internal flat networks using NTLM and Kerberos ticket reuse techniques.
* **Active Directory Security Engineers & Blue Teamers:** Audit Kerberos ticket lifetime policies, detect Kerberoasting/AS-REP roasting events, and monitor WMI persistence.
* **Cybersecurity Students:** Gain hands-on practice with industry-standard offensive tools like Rubeus, Mimikatz, BloodHound, and Impacket.

---

## Disclaimer

All lab links provided in this repository direct to official training environments hosted on Learn SecByte. All materials and exercises are provided strictly for educational purposes, defensive skill building, and authorized security research. Unauthorized testing against external production infrastructure is strictly prohibited.
