   - **Purpose**: Network discovery via ARP requests.
   - **Usage**: Identify live hosts on a local network.
   - **Syntax Examples**:
     - Live host discovery:
       ```bash
       sudo netdiscover -r <IP range>
       ```
   - **When to Use**: Use **Netdiscover** when targeting internal networks to identify live hosts.

`netdiscover` is a network discovery tool used to identify active hosts on a network. It performs ARP (Address Resolution Protocol) scans to discover devices connected to the network. Below are the key commands and options for using `netdiscover`.

1. **Basic Network Scan:**
   - **Description:** Perform a basic scan on the local network.
   - **Command:**
     ```bash
     netdiscover
     ```
   - **Example:**
     ```bash
     netdiscover
     ```
   - **Output:** Displays a list of active hosts on the network with their IP addresses, MAC addresses, and vendor information.

2. **Scan a Specific Range:**
   - **Description:** Scan a specific IP range.
   - **Command:**
     ```bash
     netdiscover -r 192.168.1.0/24
     ```
   - **Example:**
     ```bash
     netdiscover -r 10.0.0.0/8
     ```
   - **Output:** Provides details of active hosts within the specified IP range.

3. **Use a Specific Network Interface:**
   - **Description:** Specify which network interface to use for scanning.
   - **Command:**
     ```bash
     netdiscover -i eth0
     ```
   - **Example:**
     ```bash
     netdiscover -i wlan0
     ```
   - **Output:** Performs the scan using the specified network interface.

4. **Set Scan Delay:**
   - **Description:** Adjust the delay between ARP requests.
   - **Command:**
     ```bash
     netdiscover -d 2
     ```
   - **Example:**
     ```bash
     netdiscover -d 5
     ```
   - **Output:** Sets a delay of 2 or 5 seconds between ARP requests.

5. **Enable Verbose Output:**
   - **Description:** Show detailed output during the scan.
   - **Command:**
     ```bash
     netdiscover -v
     ```
   - **Example:**
     ```bash
     netdiscover -v
     ```
   - **Output:** Provides detailed information about the scan process and results.

6. **Scan in Passive Mode:**
   - **Description:** Perform a passive scan to only listen for ARP requests and responses.
   - **Command:**
     ```bash
     netdiscover -p
     ```
   - **Example:**
     ```bash
     netdiscover -p
     ```
   - **Output:** Displays detected devices without actively sending ARP requests.

7. **Show Help and Options:**
   - **Description:** Display available commands and options for `netdiscover`.
   - **Command:**
     ```bash
     netdiscover -h
     ```
   - **Example:**
     ```bash
     netdiscover -h
     ```
   - **Output:** Lists available commands and options with descriptions.

### **Installation**

To install `netdiscover`, you can use your system’s package manager:

```bash
# For Debian-based systems
sudo apt-get install netdiscover

# For Red Hat-based systems
sudo yum install netdiscover

# For macOS using Homebrew (requires additional tools)
brew install netdiscover
```

### **Usage Notes**

- `netdiscover` is useful for quickly identifying devices on a network, but it may not work effectively if the network uses VLANs or other advanced configurations.
- The `netdiscover` tool relies on ARP requests, so it might not detect devices that do not respond to ARP requests.