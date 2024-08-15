- **Purpose**: Network scanning, port scanning, and service discovery.
- **Usage**: Ideal for identifying open ports, services, and basic OS fingerprinting.

Here’s a detailed list of **Nmap options** with their **use cases** and **examples** for each:

### 1. **Basic Scanning Options**
   - **`nmap <target>`**: Perform a default scan (TCP SYN scan on the top 1000 ports).
     - **Example**: 
       ```bash
       nmap 192.168.1.1
       ```
     - **Use Case**: When you need to quickly find open ports on a target without customization.

   - **`nmap -p <port>`**: Scan a specific port or range of ports.
     - **Example**: 
       ```bash
       nmap -p 80,443 192.168.1.1
       nmap -p 1-1000 192.168.1.1
       ```
     - **Use Case**: Use this when targeting specific ports, like scanning for HTTP (80) and HTTPS (443) or a range of ports.

   - **`nmap -p-`**: Scan all 65,535 TCP ports.
     - **Example**: 
       ```bash
       nmap -p- 192.168.1.1
       ```
     - **Use Case**: When you need a complete view of all open TCP ports on a target system.

### 2. **Service and Version Detection**
   - **`nmap -sV`**: Detect the version of services running on open ports.
     - **Example**: 
       ```bash
       nmap -sV 192.168.1.1
       ```
     - **Use Case**: When you need to know the exact software version of services running on open ports (e.g., Apache 2.4.41, OpenSSH 7.6).

   - **`nmap -A`**: Aggressive scan (includes OS detection, version detection, script scanning, and traceroute).
     - **Example**: 
       ```bash
       nmap -A 192.168.1.1
       ```
     - **Use Case**: Use this for a detailed scan that gathers extensive information, such as service versions, OS detection, and network topology.

### 3. **Operating System Detection**
   - **`nmap -O`**: OS detection (tries to identify the operating system of the target).
     - **Example**: 
       ```bash
       nmap -O 192.168.1.1
       ```
     - **Use Case**: When you want to determine the operating system running on the target.

### 4. **Stealth Scanning (Avoid Detection)**
   - **`nmap -sS`**: SYN scan (stealth scan that doesn’t complete the TCP handshake).
     - **Example**: 
       ```bash
       nmap -sS 192.168.1.1
       ```
     - **Use Case**: When you want to scan a target without establishing full connections to the ports (less detectable by firewalls and IDS).

   - **`nmap -sF`**: FIN scan (sends FIN packets to probe for open ports).
     - **Example**: 
       ```bash
       nmap -sF 192.168.1.1
       ```
     - **Use Case**: Useful in environments where SYN scans are blocked by firewalls.

   - **`nmap -sN`**: TCP NULL scan (sends packets with no TCP flags set).
     - **Example**: 
       ```bash
       nmap -sN 192.168.1.1
       ```
     - **Use Case**: When performing a stealthy scan to evade detection by firewall rules or intrusion detection systems.

### 5. **UDP Scanning**
   - **`nmap -sU`**: UDP scan (used to discover open UDP ports).
     - **Example**: 
       ```bash
       nmap -sU 192.168.1.1
       ```
     - **Use Case**: When you need to find open UDP ports like DNS (53) or SNMP (161), which are not scanned by default.

### 6. **Script Scanning (Nmap Scripting Engine - NSE)**
   - **`nmap -sC`**: Run default scripts (NSE).
     - **Example**: 
       ```bash
       nmap -sC 192.168.1.1
       ```
     - **Use Case**: Use when you want to automatically run a set of default Nmap scripts to gather additional information about the target (e.g., vulnerability checks).

   - **`nmap --script <script-name>`**: Run specific scripts from the NSE library.
     - **Example**: 
       ```bash
       nmap --script vuln 192.168.1.1
       ```
     - **Use Case**: Use when you want to run targeted scripts such as vulnerability detection scripts (e.g., for Heartbleed or SMB vulnerabilities).

### 7. **Traceroute and Network Topology**
   - **`nmap --traceroute`**: Perform a traceroute alongside the port scan.
     - **Example**: 
       ```bash
       nmap --traceroute 192.168.1.1
       ```
     - **Use Case**: When you need to map out the route to the target or get a sense of network topology.

### 8. **Scanning Multiple Targets**
   - **`nmap <target1> <target2>`**: Scan multiple IPs.
     - **Example**: 
       ```bash
       nmap 192.168.1.1 192.168.1.2
       ```
     - **Use Case**: When you need to scan multiple IP addresses at once.

   - **`nmap 192.168.1.1/24`**: Scan a range of IP addresses using CIDR notation.
     - **Example**: 
       ```bash
       nmap 192.168.1.1/24
       ```
     - **Use Case**: When scanning an entire subnet of devices.

   - **`nmap -iL <file>`**: Scan a list of IPs from a file.
     - **Example**: 
       ```bash
       nmap -iL targets.txt
       ```
     - **Use Case**: Use when you want to scan a large list of targets stored in a file.

### 9. **Output Options**
   - **`nmap -oN <filename>`**: Normal output to a file.
     - **Example**: 
       ```bash
       nmap -oN scan_results.txt 192.168.1.1
       ```
     - **Use Case**: When you want to save your scan results in a simple, human-readable format.

   - **`nmap -oG <filename>`**: Grepable output.
     - **Example**: 
       ```bash
       nmap -oG scan_results.gnmap 192.168.1.1
       ```
     - **Use Case**: When you need to save results in a format that can easily be parsed with tools like `grep`.

   - **`nmap -oX <filename>`**: XML output.
     - **Example**: 
       ```bash
       nmap -oX scan_results.xml 192.168.1.1
       ```
     - **Use Case**: When you need to save the output in XML format for further processing with other tools (e.g., for integration into automated systems).

   - **`nmap -oA <basename>`**: Save output in all three formats (normal, grepable, XML).
     - **Example**: 
       ```bash
       nmap -oA scan_results 192.168.1.1
       ```
     - **Use Case**: When you want to generate all output formats at once.

### 10. **Timing and Performance**
   - **`nmap -T<0-5>`**: Timing template to control the speed of the scan (0 = slowest, 5 = fastest).
     - **Example**: 
       ```bash
       nmap -T4 192.168.1.1
       ```
     - **Use Case**: Use `T0` or `T1` for stealth, and `T4` or `T5` for faster scans.

   - **`nmap --max-retries <number>`**: Set the maximum number of retries for a port scan.
     - **Example**: 
       ```bash
       nmap --max-retries 2 192.168.1.1
       ```
     - **Use Case**: When you want to limit retries to speed up the scan.

   - **`nmap --max-rate <number>`**: Set the maximum packet transmission rate (useful for rate-limiting).
     - **Example**: 
       ```bash
       nmap --max-rate 1000 192.168.1.1
       ```
     - **Use Case**: When scanning networks where you need to avoid overloading the target with traffic.

### 11. **Evading Firewalls and IDS**
   - **`nmap -D <decoy1,decoy2,...>`**: Use decoy IPs to confuse IDS/IPS systems.
     - **Example**: 
       ```bash
       nmap -D RND:10 192.168.1.1
       ```
     - **Use Case**: Use

 when you want to evade detection by making it look like the scan is coming from multiple sources.

   - **`nmap -S <spoofed-IP>`**: Spoof the source IP address.
     - **Example**: 
       ```bash
       nmap -S 192.168.1.100 192.168.1.1
       ```
     - **Use Case**: Use to spoof the source of your scan, often to evade detection.

   - **`nmap --mtu <value>`**: Fragment packets to a specific size.
     - **Example**: 
       ```bash
       nmap --mtu 16 192.168.1.1
       ```
     - **Use Case**: Use when you need to bypass firewalls by sending fragmented packets.

### 12. **IPv6 Scanning**
   - **`nmap -6 <target>`**: Enable IPv6 scanning.
     - **Example**: 
       ```bash
       nmap -6 2001:db8::ff00:42:8329
       ```
     - **Use Case**: When the target has an IPv6 address or you’re testing an IPv6-enabled network.

### 13. **Ping Scan**
   - **`nmap -sn`**: Disable port scanning and perform a ping scan only.
     - **Example**: 
       ```bash
       nmap -sn 192.168.1.0/24
       ```
     - **Use Case**: Use this to identify live hosts on a network without scanning for open ports.

### 14. **Firewall Bypassing**
   - **`nmap -PN`**: Disable host discovery (assumes the host is up, useful when ICMP requests are blocked).
     - **Example**: 
       ```bash
       nmap -PN 192.168.1.1
       ```
     - **Use Case**: Use when the target blocks ping requests or when you suspect a firewall is blocking probes.

---

These Nmap options and commands cover a wide range of scenarios, from basic port scanning to advanced network mapping, stealth, and bypassing firewall rules.