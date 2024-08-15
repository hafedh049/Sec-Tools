Here’s a comprehensive list of **DirBuster** options along with **examples** and **use cases**. DirBuster is a GUI-based tool used to brute-force directories and files on web servers, often used to find hidden resources like admin panels, configuration files, or other sensitive data.

### 1. **URL to Scan**
   - **Option**: Enter in the **Target URL** field.
   - **Description**: Specifies the target URL or IP address to brute-force directories and files.
   - **Example**:
     ```scss
     http://example.com
     http://192.168.1.1
     ```
   - **Use Case**: Use this option to define the target you want to scan for hidden directories and files.

### 2. **Port**
   - **Option**: Enter in the **Port** field.
   - **Description**: Specifies the port on which the web server is running. Common ports are 80 (HTTP) and 443 (HTTPS).
   - **Example**:
     ```scss
     Port: 80
     Port: 8080
     ```
   - **Use Case**: Use this option to specify the correct port if the web service is running on a non-standard port (e.g., 8080).

### 3. **Select List Type**
   - **Option**: **File** or **Directory** selection.
   - **Description**: Choose between brute-forcing directories or files, depending on what you are trying to discover.
   - **Example**:
     ```scss
     Select "Directory" to search for hidden directories
     Select "File" to search for hidden files
     ```
   - **Use Case**: Use this option when you are focusing on finding either hidden directories or files based on your target and goal.

### 4. **Wordlist Selection**
   - **Option**: Select the **File** option and choose a wordlist from your system.
   - **Description**: Specifies the wordlist used for brute-forcing directories and files. DirBuster provides its own wordlists, but you can also use custom ones.
   - **Example**:
     ```scss
     /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt
     ```
   - **Use Case**: Use a wordlist suitable for the scope of the target. For a large-scale scan, use larger wordlists like `common.txt` or custom lists if targeting specific environments.

### 5. **File Extensions**
   - **Option**: **File Extension(s)**
   - **Description**: Specifies file extensions to append to the words in the wordlist for brute-forcing (useful for file enumeration).
   - **Example**:
     ```scss
     php, html, txt, jsp
     ```
   - **Use Case**: Use this option to brute-force hidden files of specific types such as `.php`, `.html`, or `.txt`. For example, targeting an Apache server might include `.php` or `.html` files.

### 6. **Number of Threads**
   - **Option**: **Number of Threads**
   - **Description**: Set the number of concurrent threads to run the scan.
   - **Example**:
     ```scss
     10, 50, 100
     ```
   - **Use Case**: Use higher thread counts for faster scans, but be careful not to overwhelm the target web server, which could trigger rate-limiting or lockouts.

### 7. **Recursive Scan**
   - **Option**: **Recursive Mode**
   - **Description**: Enables recursive brute-forcing of discovered directories (continues to scan each directory found).
   - **Example**:
     ```scss
     Enable Recursive Mode
     ```
   - **Use Case**: Use this option when you want to scan subdirectories discovered during the initial scan, allowing for a deeper search of the target.

### 8. **Advanced Scanning**
   - **Option**: **Brute Force**
   - **Description**: Enables brute-forcing directories or files with specified character sets and lengths. This is slower but more thorough.
   - **Example**:
     ```scss
     Brute Force Character Set: abcdefghijklmnopqrstuvwxyz0123456789
     Min Length: 1
     Max Length: 5
     ```
   - **Use Case**: Use this for highly customized scans when wordlists aren't available or if you want to exhaustively search all possible directory/file names.

### 9. **Auto-Stop**
   - **Option**: **Auto-stop on 4xx Errors**
   - **Description**: Stops the scan if too many 404 errors or other non-relevant HTTP status codes are encountered.
   - **Example**:
     ```scss
     Stop after 100 404 errors
     ```
   - **Use Case**: Use this option to stop the scan automatically when too many irrelevant results (like 404 Not Found errors) are encountered. It helps avoid wasting time on unproductive scans.

### 10. **Proxy Settings**
   - **Option**: **Use Proxy**
   - **Description**: Allows you to route your requests through a proxy, such as Burp Suite, for interception and analysis.
   - **Example**:
     ```scss
     Proxy Host: 127.0.0.1
     Proxy Port: 8080
     ```
   - **Use Case**: Use this option when you need to analyze your traffic or bypass firewalls, such as using Burp Suite as a proxy to view all requests/responses.

### 11. **Custom User-Agent**
   - **Option**: **Custom User-Agent**
   - **Description**: Set a custom User-Agent string for the requests.
   - **Example**:
     ```scss
     Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:91.0) Gecko/20100101 Firefox/91.0
     ```
   - **Use Case**: Use this when you need to bypass web application firewalls (WAF) or avoid blocking by using a common User-Agent string like that of a browser or bot.

### 12. **Follow Redirects**
   - **Option**: **Follow Redirects**
   - **Description**: Enables following HTTP redirects (e.g., 301 or 302 status codes).
   - **Example**:
     ```scss
     Enable Follow Redirects
     ```
   - **Use Case**: Use when the target web server employs redirection, and you want to continue brute-forcing on the redirected URL.

### 13. **Skip 4xx Codes**
   - **Option**: **Skip 4xx Codes**
   - **Description**: Skips scanning when encountering specific HTTP 4xx codes (client errors), like 403 or 404.
   - **Example**:
     ```scss
     Skip 403, 404
     ```
   - **Use Case**: Use when you want to avoid unnecessary 403 (Forbidden) or 404 (Not Found) errors and focus only on valid results.

### 14. **Save Output**
   - **Option**: **Output file**
   - **Description**: Save the scan results to a file for later review.
   - **Example**:
     ```scss
     /home/user/dirbuster_scan_results.txt
     ```
   - **Use Case**: Use this option when you need to save the results for documentation, analysis, or sharing with teammates.

### 15. **Target IP Mode**
   - **Option**: **Target IP**
   - **Description**: Directly scans the target's IP address instead of its hostname.
   - **Example**:
     ```scss
     Target IP: 192.168.1.100
     ```
   - **Use Case**: Use this option when scanning targets that do not resolve to a hostname or when you want to scan a specific IP address.

### 16. **Start from Specific Path**
   - **Option**: **Base Directory**
   - **Description**: Set a specific starting point for scanning (useful when you know where to begin scanning).
   - **Example**:
     ```scss
     Base Directory: /admin
     ```
   - **Use Case**: Use when you already know the base directory or suspect hidden resources under a specific path.

### 17. **Filter Size-based Responses**
   - **Option**: **Filter by response size**
   - **Description**: Filters results based on the response size to avoid false positives (e.g., error pages).
   - **Example**:
     ```scss
     Filter responses over 1024 bytes
     ```
   - **Use Case**: Use this option when the web server returns pages with consistent size for errors or irrelevant content, and you want to focus only on useful responses.

---

### Example Usage Scenarios:
- **Finding Hidden Admin Pages**:
   - Use a directory wordlist with extensions like `.php`, `.html`, and `.txt` to brute-force and locate admin login pages or configuration files.
     ```scss
     http://example.com:80
     Wordlist: /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
     Extensions: php, html, txt
     ```
   - Enable recursive mode to explore subdirectories like `/admin` or `/config`.

- **Discovering Sensitive Files**:
   - Use a file-based wordlist to search for backup files (`.bak`, `.old`) or logs (`.log`).
     ```scss
     http://example.com
     Wordlist: /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
     Extensions: bak, log, old
     ```

- **Subdomain Brute-forcing** (similar to Gobuster's vhost mode):
   - You can configure DirBuster for vhost enumeration using DNS wordlists, especially when looking for hidden subdomains like `admin.example.com`.

DirBuster's flexibility with various options like recursion, extensions, custom User-Agent, proxy support, and more makes it a powerful tool for web application reconnaissance. It is best suited for cases where GUI-based scanning is preferred, and detailed results are required.