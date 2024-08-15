   - **Purpose**: Retrieves domain registration details.
   - **Usage**: Information about the domain owner, registration, contact details, etc.
   - **Syntax Examples**:
     - Querying domain registration:
       ```css
       whois <domain>
       ```
   - **When to Use**: Use it when you need basic domain ownership and contact details, typically as part of passive information gathering.

`whois` is a command-line utility used to query the WHOIS database for information about domain names, IP addresses, and registrants. Below are the key commands and options for using `whois`.

1. **Basic Domain Query:**
   - **Description:** Retrieve WHOIS information for a domain.
   - **Command:**
     ```bash
     whois example.com
     ```
   - **Example:**
     ```bash
     whois google.com
     ```
   - **Output:** Displays registration details, registrant information, and domain status.

2. **Query IP Address Information:**
   - **Description:** Retrieve WHOIS information for an IP address.
   - **Command:**
     ```bash
     whois 8.8.8.8
     ```
   - **Example:**
     ```bash
     whois 192.168.1.1
     ```
   - **Output:** Provides information about the IP address, including the organization and contact details.

3. **Specify WHOIS Server:**
   - **Description:** Query a specific WHOIS server.
   - **Command:**
     ```bash
     whois -h whois.server.com example.com
     ```
   - **Example:**
     ```bash
     whois -h whois.internic.net example.com
     ```
   - **Output:** Queries the specified WHOIS server for the domain information.

4. **Show Detailed Output:**
   - **Description:** Display verbose output with more detailed information.
   - **Command:**
     ```bash
     whois -v example.com
     ```
   - **Example:**
     ```bash
     whois -v google.com
     ```
   - **Output:** Provides detailed information including registrar, registration dates, and status.

5. **Limit Output to Specific Fields:**
   - **Description:** Filter the output to show only specific fields.
   - **Command:**
     ```bash
     whois example.com | grep "Registrant Name"
     ```
   - **Example:**
     ```bash
     whois example.com | grep "Admin Email"
     ```
   - **Output:** Filters the WHOIS results to display only the registrant or admin email address.

6. **Save Output to File:**
   - **Description:** Save WHOIS query results to a file.
   - **Command:**
     ```bash
     whois example.com > whois_results.txt
     ```
   - **Example:**
     ```bash
     whois google.com > google_whois.txt
     ```
   - **Output:** Saves the WHOIS information to `whois_results.txt` or `google_whois.txt`.

7. **Check Domain Availability:**
   - **Description:** Check if a domain is available (requires parsing of WHOIS output).
   - **Command:**
     ```bash
     whois example.com | grep "No match"
     ```
   - **Example:**
     ```bash
     whois example.com | grep "Not found"
     ```
   - **Output:** Checks for the availability of the domain by looking for "No match" or "Not found" in the output.

8. **Query Multiple Domains:**
   - **Description:** Query WHOIS information for multiple domains in a file.
   - **Command:**
     ```bash
     while read domain; do whois $domain; done < domains.txt
     ```
   - **Example:**
     ```bash
     while read domain; do whois $domain; done < domains_list.txt > all_whois_results.txt
     ```
   - **File `domains.txt` Content:**
     ```
     example.com
     google.com
     ```
   - **Output:** Queries each domain listed in `domains.txt` and saves results to `all_whois_results.txt`.

9. **Show Help and Options:**
   - **Description:** Display available commands and options.
   - **Command:**
     ```bash
     whois --help
     ```
   - **Example:**
     ```bash
     whois --help
     ```
   - **Output:** Lists available options and usage instructions.

### **Installation**

The `whois` command is typically included in most Linux distributions by default. If it's not installed, you can usually install it via your package manager:

```bash
# For Debian-based systems
sudo apt-get install whois

# For Red Hat-based systems
sudo yum install whois

# For macOS using Homebrew
brew install whois
```

### **Usage Notes**

- The format and content of WHOIS information can vary depending on the domain registrar and the WHOIS server used.
- Some WHOIS servers may have rate limits or restrictions on the number of queries you can perform in a given time period.

Let me know if you need further details or additional examples!