- **Purpose**: Directory and subdomain brute-forcing, used for web enumeration.
- **Usage**: Discover hidden directories and files on a web server.

Gobuster is a powerful tool used for directory and subdomain brute-forcing, and it offers a wide range of options for various use cases. Below is a comprehensive list of **Gobuster options** along with **examples** and **use cases**:

### 1. **Basic Directory Brute-Forcing**
   - **Command**: `gobuster dir`
   - **Description**: This option is used to brute-force directories and files on web servers.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /path/to/wordlist.txt
     ```
   - **Use Case**: Use this to discover hidden directories and files on a web server by brute-forcing.

### 2. **URL to Scan (`-u`)**
   - **Option**: `-u <URL>`
   - **Description**: Specifies the target URL for directory or file enumeration.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirb/common.txt
     ```
   - **Use Case**: Use this option to define the target URL for brute-forcing directories or files.

### 3. **Wordlist (`-w`)**
   - **Option**: `-w <wordlist>`
   - **Description**: Specifies the wordlist to use for the brute-forcing.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
     ```
   - **Use Case**: Use a custom or common wordlist (like those in SecLists or Dirbuster) for directory brute-forcing.

### 4. **File Extension (`-x`)**
   - **Option**: `-x <extensions>`
   - **Description**: Appends file extensions to each word in the wordlist (for file enumeration).
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt
     ```
   - **Use Case**: Use when you are brute-forcing files and want to include specific extensions (e.g., `.php`, `.html`, `.txt`).

### 5. **Status Codes to Display (`-s`)**
   - **Option**: `-s <codes>`
   - **Description**: Only display results that return specific HTTP status codes (e.g., 200 for OK, 301 for redirection).
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -s 200,301
     ```
   - **Use Case**: Use when you want to filter responses by specific status codes, such as showing only 200 OK responses.

### 6. **Set Timeout (`-t`)**
   - **Option**: `-t <threads>`
   - **Description**: Set the number of concurrent threads for scanning.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 50
     ```
   - **Use Case**: Use when you need to adjust the speed of the brute-force scan by specifying more or fewer threads. Higher thread count increases speed but can overwhelm the target server.

### 7. **Ignore Length (`-l`)**
   - **Option**: `-l`
   - **Description**: Do not hide length-based results, which may otherwise be excluded to avoid false positives.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -l
     ```
   - **Use Case**: Use this option when you want to see all results, including those that might be filtered out due to similar lengths.

### 8. **Output to File (`-o`)**
   - **Option**: `-o <output-file>`
   - **Description**: Save the results of the scan to a file.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -o results.txt
     ```
   - **Use Case**: Use when you need to save the results for later review, documentation, or sharing.

### 9. **Exclude Lengths (`--exclude-length`)**
   - **Option**: `--exclude-length <length>`
   - **Description**: Exclude results that match a specific length of the HTTP response body.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt --exclude-length 1234
     ```
   - **Use Case**: Use to avoid false positives by excluding responses that have a known, irrelevant length.

### 10. **Use Proxy (`--proxy`)**
   - **Option**: `--proxy <proxy>`
   - **Description**: Use a proxy server to route requests.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt --proxy http://127.0.0.1:8080
     ```
   - **Use Case**: Use when you need to run Gobuster through a proxy, such as Burp Suite, to inspect traffic or bypass firewalls.

### 11. **Virtual Host (Subdomain) Enumeration (`gobuster vhost`)**
   - **Command**: `gobuster vhost`
   - **Description**: Brute-force subdomains on a domain to discover hidden virtual hosts.
   - **Example**:
     ```bash
     gobuster vhost -u http://example.com -w /usr/share/wordlists/Discovery/DNS/subdomains-top1million-5000.txt
     ```
   - **Use Case**: Use for discovering subdomains of a target domain during reconnaissance.

### 12. **DNS Subdomain Enumeration (`gobuster dns`)**
   - **Command**: `gobuster dns`
   - **Description**: Brute-force DNS subdomains of a target.
   - **Example**:
     ```bash
     gobuster dns -d example.com -w /usr/share/wordlists/Discovery/DNS/subdomains-top1million-5000.txt
     ```
   - **Use Case**: Use this option when performing subdomain enumeration to discover hidden services on a target domain.

### 13. **Append a Slash to Directories (`-f`)**
   - **Option**: `-f`
   - **Description**: Forces a trailing slash `/` to be added to each directory request.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -f
     ```
   - **Use Case**: Use this to simulate directory traversal more accurately (useful for web servers that require the trailing slash).

### 14. **Follow Redirects (`-r`)**
   - **Option**: `-r`
   - **Description**: Automatically follow redirects (HTTP 3xx responses).
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -r
     ```
   - **Use Case**: Use when you want Gobuster to follow HTTP redirects and continue enumeration on redirected URLs.

### 15. **Wildcard DNS Check (`-wld`)**
   - **Option**: `-wld`
   - **Description**: Perform a wildcard DNS check to avoid false positives.
   - **Example**:
     ```bash
     gobuster dns -d example.com -w /usr/share/wordlists/Discovery/DNS/subdomains-top1million-5000.txt -wld
     ```
   - **Use Case**: Use this to eliminate false positives when performing DNS subdomain enumeration on domains with wildcard DNS enabled.

### 16. **Specify a User-Agent (`-a`)**
   - **Option**: `-a <user-agent>`
   - **Description**: Use a custom User-Agent string in the HTTP requests.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -a "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
     ```
   - **Use Case**: Use this to mimic specific browsers or crawlers or to bypass security mechanisms based on User-Agent.

### 17. **HTTP Headers (`-H`)**
   - **Option**: `-H "header: value"`
   - **Description**: Add custom HTTP headers to the requests.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -H "Authorization: Bearer TOKEN"
     ```
   - **Use Case**: Use this when targeting web applications that

 require specific headers, such as Authorization tokens or custom API headers.

### 18. **Specify HTTP Method (`-m`)**
   - **Option**: `-m <method>`
   - **Description**: Use a custom HTTP method (e.g., GET, POST, HEAD) for requests.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -m POST
     ```
   - **Use Case**: Use when you need to use a specific HTTP method like POST instead of GET.

### 19. **Rate Limit (`--delay`)**
   - **Option**: `--delay <time>`
   - **Description**: Introduce a delay between requests to avoid rate-limiting or overwhelming the target server.
   - **Example**:
     ```bash
     gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt --delay 200ms
     ```
   - **Use Case**: Use when you need to throttle the speed of requests, typically to avoid detection or rate-limiting.

---

These options cover various aspects of Gobuster’s functionality, from simple directory brute-forcing to advanced techniques like virtual host enumeration and DNS subdomain discovery. The tool’s flexibility makes it suitable for many use cases in web application and network reconnaissance.