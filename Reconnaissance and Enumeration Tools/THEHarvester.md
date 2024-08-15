  - **Purpose**: Email, subdomain, and IP reconnaissance.
   - **Usage**: Collect email addresses, domain names, subdomains, and open ports from various public sources.
   - **Syntax Examples**:
     - Gather email addresses and subdomains:
       ```bash
       theHarvester -d <domain> -l 500 -b google
       ```
   - **When to Use**: Use it to gather OSINT (Open Source Intelligence) during the early stages of testing to find emails or domains from public sources.

`theHarvester` is a reconnaissance tool used to gather email addresses, subdomains, and other information from various public sources. Below are the key commands and options for using `theHarvester`.

1. **Basic Email and Domain Enumeration:**
   - **Description:** Collect email addresses and domain information for a given domain.
   - **Command:**
     ```bash
     theHarvester -d example.com -b google
     ```
   - **Example:**
     ```bash
     theHarvester -d example.com -b google -l 500
     ```
   - **Output:** Lists collected emails and domain information from Google.

2. **Specify Data Sources:**
   - **Description:** Use different sources for gathering information.
   - **Command:**
     ```bash
     theHarvester -d example.com -b all
     ```
   - **Example:**
     ```bash
     theHarvester -d example.com -b baidu,bing,yahoo
     ```
   - **Output:** Collects data from the specified sources like Baidu, Bing, and Yahoo.

3. **Use Multiple Domains:**
   - **Description:** Gather information for multiple domains.
   - **Command:**
     ```bash
     theHarvester -d example.com -d example.org -b google
     ```
   - **Example:**
     ```bash
     theHarvester -d example.com -d example.org -b google -l 500
     ```
   - **Output:** Collects data for both domains from Google.

4. **Limit Number of Results:**
   - **Description:** Set the maximum number of results to return.
   - **Command:**
     ```bash
     theHarvester -d example.com -b google -l 100
     ```
   - **Example:**
     ```bash
     theHarvester -d example.com -b google -l 50
     ```
   - **Output:** Limits results to 50 or 100 entries, as specified.

5. **Save Results to File:**
   - **Description:** Save the gathered information to a file.
   - **Command:**
     ```bash
     theHarvester -d example.com -b google -f results.html
     ```
   - **Example:**
     ```bash
     theHarvester -d example.com -b google -f results.txt
     ```
   - **Output:** Saves the results in `results.html` or `results.txt`.

6. **Set Output Format:**
   - **Description:** Specify the format for the output (e.g., HTML, CSV).
   - **Command:**
     ```bash
     theHarvester -d example.com -b google -f results.csv
     ```
   - **Example:**
     ```bash
     theHarvester -d example.com -b google -f results.html
     ```
   - **Output:** Results are saved in the specified format.

7. **Specify Maximum Number of Pages to Crawl:**
   - **Description:** Limit the number of pages to crawl from each data source.
   - **Command:**
     ```bash
     theHarvester -d example.com -b google -l 100 -s 2
     ```
   - **Example:**
     ```bash
     theHarvester -d example.com -b google -l 50 -s 5
     ```
   - **Output:** Specifies the start page number (`-s`) and limits the results (`-l`).

8. **Use a Custom User-Agent:**
   - **Description:** Set a custom User-Agent string for requests.
   - **Command:**
     ```bash
     theHarvester -d example.com -b google -u "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3"
     ```
   - **Example:**
     ```bash
     theHarvester -d example.com -b google -u "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Firefox/89.0"
     ```
   - **Output:** Uses the specified User-Agent for requests.

9. **Verbose Output:**
   - **Description:** Enable verbose output for more detailed information.
   - **Command:**
     ```bash
     theHarvester -d example.com -b google -v
     ```
   - **Example:**
     ```bash
     theHarvester -d example.com -b google -v -l 100
     ```
   - **Output:** Provides detailed information during the scan.

10. **Show Help and Options:**
    - **Description:** Display available commands and options.
    - **Command:**
      ```bash
      theHarvester -h
      ```
    - **Example:**
      ```bash
      theHarvester -h
      ```
    - **Output:** Lists available commands and options with descriptions.

### **Installation**

To install `theHarvester`, you can use Python's package manager `pip`:

```bash
pip install theharvester
```

Or clone and install from the GitHub repository:

```bash
git clone https://github.com/laramies/theHarvester.git
cd theHarvester
pip install -r requirements.txt
```

### **Usage Notes**

- The availability of data sources and the effectiveness of the tool may vary depending on the version and the public APIs available.
- Use the `-h` option to get the latest help information and options for the installed version of `theHarvester`.