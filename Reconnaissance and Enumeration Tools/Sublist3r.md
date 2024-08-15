
   - **Purpose**: Subdomain enumeration tool.
   - **Usage**: Enumerates subdomains across different public sources.
   - **Syntax Examples**:
     - Subdomain discovery:
       ```bash
       sublist3r -d <domain>
       ```
   - **When to Use**: Use Sublist3r when gathering information about a domain's subdomains.


`Sublist3r` is a tool designed for enumerating subdomains of websites using various search engines and APIs. It is useful for discovering subdomains that may not be immediately obvious.

1. **Basic Subdomain Enumeration:**
   - **Description:** Discover subdomains for a target domain.
   - **Command:**
     ```bash
     sublist3r -d example.com
     ```
   - **Example:**
     ```bash
     sublist3r -d google.com
     ```
   - **Output:** Lists discovered subdomains for the specified domain.

2. **Scan Multiple Domains:**
   - **Description:** Scan multiple domains from a file.
   - **Command:**
     ```bash
     sublist3r -d example.com -d anotherexample.com
     ```
   - **Example:**
     ```bash
     sublist3r -d example.com -d anotherexample.com
     ```
   - **Output:** Provides subdomains for each domain specified.

3. **Use Multiple Domain Enumeration Engines:**
   - **Description:** Use different search engines and APIs for enumeration.
   - **Command:**
     ```bash
     sublist3r -d example.com -b
     ```
   - **Example:**
     ```bash
     sublist3r -d google.com -b
     ```
   - **Output:** Uses various enumeration engines to find subdomains.

4. **Save Results to File:**
   - **Description:** Save the discovered subdomains to a file.
   - **Command:**
     ```bash
     sublist3r -d example.com -o results.txt
     ```
   - **Example:**
     ```bash
     sublist3r -d google.com -o google_subdomains.txt
     ```
   - **Output:** Saves the list of subdomains to `results.txt` or `google_subdomains.txt`.

5. **Enable Verbose Output:**
   - **Description:** Show detailed output during enumeration.
   - **Command:**
     ```bash
     sublist3r -d example.com -v
     ```
   - **Example:**
     ```bash
     sublist3r -d google.com -v
     ```
   - **Output:** Provides detailed output and progress information.

6. **Use Specific APIs:**
   - **Description:** Use specific APIs for subdomain enumeration (requires API keys).
   - **Command:**
     ```bash
     sublist3r -d example.com --dnsdb-api-key YOUR_API_KEY
     ```
   - **Example:**
     ```bash
     sublist3r -d google.com --virustotal-api-key YOUR_API_KEY
     ```
   - **Output:** Utilizes the specified APIs for enhanced enumeration.

7. **Specify a Custom Wordlist:**
   - **Description:** Use a custom wordlist for brute-force subdomain enumeration.
   - **Command:**
     ```bash
     sublist3r -d example.com -w /path/to/wordlist.txt
     ```
   - **Example:**
     ```bash
     sublist3r -d google.com -w /usr/share/wordlists/subdomains.txt
     ```
   - **Output:** Uses the specified wordlist for enumeration.

8. **Show Help and Options:**
   - **Description:** Display available commands and options for `Sublist3r`.
   - **Command:**
     ```bash
     sublist3r -h
     ```
   - **Example:**
     ```bash
     sublist3r -h
     ```
   - **Output:** Lists available commands and options with descriptions.

### **Installation**

To install `Sublist3r`, you need to clone the repository and install the necessary dependencies:

```bash
# Clone the repository
git clone https://github.com/aboul3la/Sublist3r.git
cd Sublist3r

# Install dependencies
pip install -r requirements.txt
```

### **Usage Notes**

- `Sublist3r` can be combined with other tools and techniques to enhance the discovery of subdomains.
- Some API-based enumeration methods may require API keys and may have usage limits or require registration.