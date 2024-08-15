   - **Purpose**: Subdomain enumeration and DNS enumeration.
   - **Usage**: Identify subdomains and DNS records of a target domain.
   - **Syntax Examples**:
     - Passive subdomain enumeration:
       ```bash
       amass enum -passive -d <target-domain>
       ```
     - Active DNS enumeration:
       ```bash
       amass enum -active -d <target-domain>
       ```
   - **When to Use**: Use Amass when you want to discover all subdomains of a target as part of DNS enumeration, useful in larger scale tests.


Here's a detailed guide for using `amass` from the shell, including commands, options, and examples:

---

### **Amass Shell Commands and Options**

`Amass` is a tool used for network mapping and reconnaissance, primarily for DNS enumeration and subdomain discovery. Below are some of the key commands and options you can use with `amass`.

1. **Basic Domain Enumeration:**
   - **Description:** Discover subdomains for a given domain.
   - **Command:**
     ```bash
     amass enum -d example.com
     ```
   - **Example:**
     ```bash
     amass enum -d example.com -o subdomains.txt
     ```
   - **Output:** Lists discovered subdomains and saves them to `subdomains.txt`.

2. **Perform Active Scanning:**
   - **Description:** Use active techniques to discover subdomains.
   - **Command:**
     ```bash
     amass enum -active -d example.com
     ```
   - **Example:**
     ```bash
     amass enum -active -d example.com -o active_subdomains.txt
     ```
   - **Output:** Includes results from active scanning, saved to `active_subdomains.txt`.

3. **Brute Force Subdomain Enumeration:**
   - **Description:** Use a wordlist for brute force subdomain discovery.
   - **Command:**
     ```bash
     amass enum -brute -d example.com -w /path/to/wordlist.txt
     ```
   - **Example:**
     ```bash
     amass enum -brute -d example.com -w /usr/share/wordlists/subdomains.txt -o brute_force_subdomains.txt
     ```
   - **Output:** Results from brute force enumeration are saved to `brute_force_subdomains.txt`.

4. **DNS Record Enumeration:**
   - **Description:** Perform DNS record enumeration and discover associated IP addresses.
   - **Command:**
     ```bash
     amass intel -d example.com
     ```
   - **Example:**
     ```bash
     amass intel -d example.com -o dns_records.txt
     ```
   - **Output:** DNS records and associated data saved to `dns_records.txt`.

5. **Passive Reconnaissance:**
   - **Description:** Use passive methods to find subdomains without making DNS requests.
   - **Command:**
     ```bash
     amass enum -passive -d example.com
     ```
   - **Example:**
     ```bash
     amass enum -passive -d example.com -o passive_subdomains.txt
     ```
   - **Output:** Results from passive reconnaissance, saved to `passive_subdomains.txt`.

6. **Set Multiple Domains:**
   - **Description:** Discover subdomains for multiple domains.
   - **Command:**
     ```bash
     amass enum -d example.com -d example.org
     ```
   - **Example:**
     ```bash
     amass enum -d example.com -d example.org -o multiple_domains.txt
     ```
   - **Output:** Lists subdomains for both domains, saved to `multiple_domains.txt`.

7. **Save Results in JSON Format:**
   - **Description:** Save results in JSON format for easier integration with other tools.
   - **Command:**
     ```bash
     amass enum -d example.com -o json -o results.json
     ```
   - **Example:**
     ```bash
     amass enum -d example.com -o json -o results.json
     ```
   - **Output:** Results saved in JSON format to `results.json`.

8. **Use Custom Configurations:**
   - **Description:** Specify custom configuration files for `amass`.
   - **Command:**
     ```bash
     amass enum -d example.com -cf /path/to/config.ini
     ```
   - **Example:**
     ```bash
     amass enum -d example.com -cf /etc/amass/config.ini
     ```
   - **Output:** Uses the specified configuration file for the scan.

9. **Show Help and Options:**
   - **Description:** Display available commands and options.
   - **Command:**
     ```bash
     amass -h
     ```
   - **Example:**
     ```bash
     amass -h
     ```
   - **Output:** Provides help information and lists available commands.

### **Installation**

To install `amass`, you can use a package manager like `apt` on Debian-based systems or download pre-built binaries from the [official Amass GitHub releases page](https://github.com/OWASP/Amass/releases):

```bash
# For Debian-based systems
sudo apt-get install amass

# Or download the binary manually
wget https://github.com/OWASP/Amass/releases/download/vX.Y.Z/amass_linux_amd64_vX.Y.Z.tar.gz
tar -xzf amass_linux_amd64_vX.Y.Z.tar.gz
sudo mv amass /usr/local/bin/
```

Replace `vX.Y.Z` with the version number you want to install.

### **Usage Notes**

- Always refer to the latest documentation for `amass` to get updated commands and options.
- Customize `amass` commands based on your specific reconnaissance needs