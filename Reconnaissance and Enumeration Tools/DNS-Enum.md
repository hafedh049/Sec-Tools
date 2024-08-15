
   - **Purpose**: DNS enumeration.
   - **Usage**: Enumerate DNS records and subdomains for a given domain.
   - **Syntax Examples**:
     - DNS enumeration:
       ```bash
       dnsenum <domain>
       ```
   - **When to Use**: Use Dnsenum when performing DNS reconnaissance, including DNS zone transfers and subdomain discovery.

`dnsenum` is a tool used for DNS enumeration and can be useful in gathering information about domain names and their associated records. Below are the key commands and options for using `dnsenum`.

1. **Basic Domain Enumeration:**
   - **Description:** Perform a basic DNS enumeration for a given domain.
   - **Command:**
     ```bash
     dnsenum example.com
     ```
   - **Example:**
     ```bash
     dnsenum google.com
     ```
   - **Output:** Provides DNS information including A, MX, and NS records, along with possible subdomains.

2. **Brute Force Subdomain Enumeration:**
   - **Description:** Use a wordlist to brute force subdomains.
   - **Command:**
     ```bash
     dnsenum --enum -d example.com -w /path/to/wordlist.txt
     ```
   - **Example:**
     ```bash
     dnsenum --enum -d google.com -w /usr/share/wordlists/subdomains.txt
     ```
   - **Output:** Attempts to find subdomains using the specified wordlist.

3. **Perform Reverse DNS Lookup:**
   - **Description:** Perform a reverse DNS lookup for IP addresses.
   - **Command:**
     ```bash
     dnsenum --reverselookup -d example.com
     ```
   - **Example:**
     ```bash
     dnsenum --reverselookup -d google.com
     ```
   - **Output:** Provides reverse DNS records for the domain's IP addresses.

4. **Retrieve DNS Records:**
   - **Description:** Retrieve various DNS records (A, MX, NS, TXT, etc.).
   - **Command:**
     ```bash
     dnsenum --dns -d example.com
     ```
   - **Example:**
     ```bash
     dnsenum --dns -d google.com
     ```
   - **Output:** Displays various DNS records for the domain.

5. **Use Custom DNS Server:**
   - **Description:** Query a specific DNS server for the records.
   - **Command:**
     ```bash
     dnsenum --server 8.8.8.8 -d example.com
     ```
   - **Example:**
     ```bash
     dnsenum --server 1.1.1.1 -d google.com
     ```
   - **Output:** Uses the specified DNS server for queries.

6. **Enable Verbose Output:**
   - **Description:** Show detailed information during the enumeration.
   - **Command:**
     ```bash
     dnsenum -v -d example.com
     ```
   - **Example:**
     ```bash
     dnsenum -v -d google.com
     ```
   - **Output:** Provides verbose output with additional details about the DNS records and enumeration process.

7. **Save Results to File:**
   - **Description:** Save the results of the enumeration to a file.
   - **Command:**
     ```bash
     dnsenum -d example.com -o results.txt
     ```
   - **Example:**
     ```bash
     dnsenum -d google.com -o google_results.txt
     ```
   - **Output:** Saves the results to `results.txt` or `google_results.txt`.

8. **Show Help and Options:**
   - **Description:** Display available commands and options for `dnsenum`.
   - **Command:**
     ```bash
     dnsenum --help
     ```
   - **Example:**
     ```bash
     dnsenum --help
     ```
   - **Output:** Lists available commands and options with descriptions.

### **Installation**

To install `dnsenum`, you can typically use a package manager or download it from its repository. For example:

```bash
# For Debian-based systems
sudo apt-get install dnsenum

# For installing from source or GitHub repository
git clone https://github.com/fwaeytens/dnsenum.git
cd dnsenum
chmod +x dnsenum.pl
sudo cp dnsenum.pl /usr/local/bin/dnsenum
```

### **Usage Notes**

- `dnsenum` relies on various DNS queries and may require appropriate permissions or configurations to execute effectively.
- The output format may vary based on the options used and the version of `dnsenum`.

Let me know if you need further details or additional examples!