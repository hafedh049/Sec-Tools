 - **Purpose**: High-speed port scanning.
   - **Usage**: Similar to Nmap but faster, it scans a massive range of IPs or ports quickly.
   - **Syntax Examples**:
     - Full port scan:
       ```bash
       masscan -p0-65535 <target-ip> --rate=10000
       ```
   - **When to Use**: Use Masscan when you need to scan large networks or large port ranges in a very short amount of time.

`masscan` is a high-performance network scanner used for discovering open ports and services across large networks. Below are the key commands and options for using `masscan`.

1. **Basic Port Scan:**
   - **Description:** Scan a range of IP addresses for open ports.
   - **Command:**
     ```bash
     masscan -p80,443 192.168.1.0/24
     ```
   - **Example:**
     ```bash
     masscan -p22,80,443 10.0.0.0/8
     ```
   - **Output:** Lists open ports on the specified IP range.

2. **Scan All Ports:**
   - **Description:** Scan all 65535 ports on a target IP or IP range.
   - **Command:**
     ```bash
     masscan -p0-65535 192.168.1.1
     ```
   - **Example:**
     ```bash
     masscan -p0-65535 10.0.0.1
     ```
   - **Output:** Provides a comprehensive list of open ports.

3. **Specify Scan Rate:**
   - **Description:** Adjust the scan rate to control how quickly scans are performed.
   - **Command:**
     ```bash
     masscan -p80,443 192.168.1.0/24 --rate 1000
     ```
   - **Example:**
     ```bash
     masscan -p80,443 10.0.0.0/8 --rate 5000
     ```
   - **Output:** Sets the number of packets per second (PPS) to control scan speed.

4. **Use Specific Network Interface:**
   - **Description:** Specify which network interface to use for the scan.
   - **Command:**
     ```bash
     masscan -p80,443 192.168.1.0/24 --interface eth0
     ```
   - **Example:**
     ```bash
     masscan -p22 10.0.0.0/8 --interface wlan0
     ```
   - **Output:** Performs the scan using the specified network interface.

5. **Save Output to File:**
   - **Description:** Save the scan results to a file.
   - **Command:**
     ```bash
     masscan -p80,443 192.168.1.0/24 -oG results.txt
     ```
   - **Example:**
     ```bash
     masscan -p22,80,443 10.0.0.0/24 -oJ scan_results.json
     ```
   - **Output:** Saves the results to `results.txt` or `scan_results.json`.

6. **Scan Specific Ports Using List:**
   - **Description:** Scan ports listed in a file.
   - **Command:**
     ```bash
     masscan -pL /path/to/ports.txt 192.168.1.0/24
     ```
   - **Example:**
     ```bash
     masscan -pL /usr/share/port-lists/common-ports.txt 10.0.0.0/8
     ```
   - **File `ports.txt` Content:**
     ```
     80
     443
     22
     ```
   - **Output:** Scans the ports listed in `ports.txt`.

7. **Perform a Scan with a Custom Source Port:**
   - **Description:** Specify a custom source port for the scan.
   - **Command:**
     ```bash
     masscan -p80,443 192.168.1.0/24 --source-port 12345
     ```
   - **Example:**
     ```bash
     masscan -p22 10.0.0.0/24 --source-port 54321
     ```
   - **Output:** Uses the specified source port for the scan.

8. **Specify Timeout:**
   - **Description:** Set the timeout for responses.
   - **Command:**
     ```bash
     masscan -p80,443 192.168.1.0/24 --timeout 1000
     ```
   - **Example:**
     ```bash
     masscan -p22,80,443 10.0.0.0/8 --timeout 2000
     ```
   - **Output:** Sets the timeout for receiving responses in milliseconds.

9. **Show Help and Options:**
   - **Description:** Display available commands and options.
   - **Command:**
     ```bash
     masscan --help
     ```
   - **Example:**
     ```bash
     masscan --help
     ```
   - **Output:** Lists available commands and options with descriptions.

### **Installation**

To install `masscan`, you can compile it from source or use pre-built binaries:

```bash
# Clone the repository
git clone https://github.com/robertdavidgraham/masscan
cd masscan

# Compile the source
make

# Install (optional)
sudo cp masscan /usr/local/bin/
```

### **Usage Notes**

- Adjust scan rates and timeouts based on network conditions and legal considerations.
- Be cautious when scanning large networks or performing high-rate scans to avoid network disruption or legal issues.