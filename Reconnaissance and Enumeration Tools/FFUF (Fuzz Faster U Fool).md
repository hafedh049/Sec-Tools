   - **Purpose**: Brute-force web directories, files, parameters, and DNS subdomains.
   - **Usage**: Fast fuzzing of directories or parameters on web applications.

Here’s a comprehensive list of **FFUF (Fuzz Faster U Fool)** options, along with **examples** and **use cases**. FFUF is a fast and versatile web fuzzing tool used for discovering directories, files, subdomains, and more through brute-forcing. Below are its key options with explanations.

### 1. **Basic Directory and File Brute-Forcing (`-u` and `-w`)**
   - **Option**: `-u <URL>` and `-w <wordlist>`
   - **Description**: Specifies the target URL and wordlist for directory or file brute-forcing.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt
     ```
   - **Use Case**: Use this to brute-force directories and files by replacing the word `FUZZ` in the URL with words from the wordlist. This is the most basic and commonly used FFUF functionality.

### 2. **Define Fuzzing Parameter (`FUZZ`)**
   - **Option**: Use `FUZZ` in the URL, header, or POST data.
   - **Description**: The keyword `FUZZ` is replaced by words from the wordlist during the fuzzing process.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt
     ```
     ```bash
     ffuf -u http://example.com -X POST -d "username=FUZZ&password=password" -w /path/to/usernames.txt
     ```
   - **Use Case**: Use this for fuzzing any part of an HTTP request, whether it's in the URL path, headers, or POST data. It’s essential for brute-forcing login forms, directories, parameters, etc.

### 3. **Set HTTP Method (`-X`)**
   - **Option**: `-X <HTTP method>`
   - **Description**: Specifies the HTTP method to use (e.g., GET, POST, PUT).
   - **Example**:
     ```bash
     ffuf -u http://example.com/login -X POST -d "username=admin&password=FUZZ" -w /path/to/passwords.txt
     ```
   - **Use Case**: Use when brute-forcing POST requests, such as login forms or API endpoints that require data submission.

### 4. **POST Data (`-d`)**
   - **Option**: `-d <data>`
   - **Description**: Specify POST data to be sent in the request.
   - **Example**:
     ```bash
     ffuf -u http://example.com/login -X POST -d "username=FUZZ&password=password" -w /path/to/usernames.txt
     ```
   - **Use Case**: Use this when brute-forcing login forms or other POST-based parameters.

### 5. **Custom Header (`-H`)**
   - **Option**: `-H "header: value"`
   - **Description**: Add custom HTTP headers to the request.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt -H "Authorization: Bearer <token>"
     ```
   - **Use Case**: Use this when the target web application requires specific headers, like authentication tokens, API keys, or custom headers for APIs.

### 6. **Output to File (`-o`)**
   - **Option**: `-o <filename>`
   - **Description**: Save the scan results to a file (supports JSON, CSV, and plain text).
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt -o output.txt
     ```
   - **Use Case**: Use when you need to save scan results for documentation or later analysis.

### 7. **Filter Results by Status Codes (`-c` and `-fc`)**
   - **Option**: `-c` (Colorize output), `-fc <status_code>`
   - **Description**: Filters results based on HTTP status codes.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt -c -fc 404
     ```
   - **Use Case**: Use this to avoid irrelevant results (like 404 Not Found errors) and focus on successful responses (e.g., 200 OK or 301 redirects).

### 8. **Match Results by Status Codes (`-mc`)**
   - **Option**: `-mc <status_code>`
   - **Description**: Match only results with specific HTTP status codes.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt -mc 200,301
     ```
   - **Use Case**: Use when you want to filter the results based on specific HTTP status codes, such as 200 (OK) or 301 (Redirect).

### 9. **Match Results by Response Size (`-fs`, `-ms`)**
   - **Option**: `-fs <size>` (filter), `-ms <size>` (match)
   - **Description**: Filters or matches responses based on their body size (in bytes).
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt -fs 1234
     ```
   - **Use Case**: Use when you want to eliminate false positives by filtering responses with specific sizes or matching only specific response sizes.

### 10. **Set Recursion Depth (`-recursion` and `-recursion-depth`)**
   - **Option**: `-recursion` (enable), `-recursion-depth <level>`
   - **Description**: Enables recursive scanning into discovered directories and sets the depth.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt -recursion -recursion-depth 3
     ```
   - **Use Case**: Use when you want to recursively brute-force directories found during the initial scan, which is useful for exploring deeply nested web directories.

### 11. **Rate Limiting (`-rate`)**
   - **Option**: `-rate <requests_per_second>`
   - **Description**: Set a limit on the number of requests per second.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt -rate 100
     ```
   - **Use Case**: Use when you need to control the rate of requests to avoid overwhelming the target server or to prevent getting rate-limited by security measures.

### 12. **Wordlist Combination (`-w` multiple times)**
   - **Option**: Multiple `-w <wordlist>` options for using multiple wordlists.
   - **Description**: Allows you to use multiple wordlists for different parameters.
   - **Example**:
     ```bash
     ffuf -u http://example.com/login?user=FUZZ&pass=FUZ2Z -w /path/to/usernames.txt -w /path/to/passwords.txt
     ```
   - **Use Case**: Use when brute-forcing multiple parameters (e.g., usernames and passwords) in one request.

### 13. **Verbose Mode (`-v`)**
   - **Option**: `-v`
   - **Description**: Enables verbose output to see all requests and responses.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt -v
     ```
   - **Use Case**: Use when you want detailed output of all requests and responses to debug issues or get more insights into the results.

### 14. **Follow Redirects (`-r`)**
   - **Option**: `-r`
   - **Description**: Automatically follow HTTP 3xx redirects during fuzzing.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt -r
     ```
   - **Use Case**: Use this when you need to follow redirects to ensure that the target of a redirected URL is also fuzzed.

### 15. **Delay Between Requests (`--delay`)**
   - **Option**: `--delay <delay_time>`
   - **Description**: Introduces a delay between requests to avoid overwhelming the server or triggering rate-limiting mechanisms.
   - **Example**:
     ```bash
     ffuf -u http://example.com/FUZZ -w /path/to/wordlist.txt --delay 0.2
     ```
   - **Use Case**: Use when targeting servers with rate-limiting or to avoid overloading the server.

### 16. **Virtual Host (VHost) Enumeration (`-H`)**
   - **Option**: `-H "Host: FUZZ.<target>"`
   - **Description**: Perform VHost enumeration by fuzzing subdomains.
   - **Example**:
     ```bash
     ffuf -u http://example.com -H "Host: FUZZ.example.com" -w /path/to/subdomains.txt
     ```
   - **Use Case**: Use when discovering subdomains by fuzzing for virtual hosts, particularly useful for finding hidden subdomains on a target.

