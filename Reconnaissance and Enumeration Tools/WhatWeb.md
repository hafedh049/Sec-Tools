   - **Purpose**: Web application fingerprinting.
   - **Usage**: Identify technologies, frameworks, and services running on a web application.
   - **Syntax Examples**:
     - Web technology detection:
       ```css
       whatweb <target>
       ```
   - **When to Use**: Use it when you need a quick and easy way to identify web technologies, such as CMS, frameworks, and plugins, during reconnaissance.

`WhatWeb` is a web application fingerprinting tool that identifies technologies used by websites. It can detect web servers, frameworks, libraries, and other technologies based on HTTP headers, HTML content, and other elements.

1. **Basic Website Fingerprinting:**
   - **Description:** Identify technologies used by a website.
   - **Command:**
     ```bash
     whatweb example.com
     ```
   - **Example:**
     ```bash
     whatweb google.com
     ```
   - **Output:** Displays detected technologies, such as web server software, CMS, frameworks, and JavaScript libraries.

2. **Scan Multiple Websites:**
   - **Description:** Scan multiple websites from a file containing URLs.
   - **Command:**
     ```bash
     whatweb -i urls.txt
     ```
   - **Example:**
     ```bash
     whatweb -i websites.txt
     ```
   - **File `urls.txt` Content:**
     ```
     example.com
     google.com
     ```
   - **Output:** Provides technology information for each website listed in `urls.txt`.

3. **Save Output to File:**
   - **Description:** Save the results of the scan to a file.
   - **Command:**
     ```bash
     whatweb example.com -o results.txt
     ```
   - **Example:**
     ```bash
     whatweb google.com -o google_results.txt
     ```
   - **Output:** Saves the fingerprinting results to `results.txt` or `google_results.txt`.

4. **Use Specific User-Agent String:**
   - **Description:** Specify a custom User-Agent string for the scan.
   - **Command:**
     ```bash
     whatweb example.com --user-agent "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36"
     ```
   - **Example:**
     ```bash
     whatweb google.com --user-agent "MyCustomAgent/1.0"
     ```
   - **Output:** Uses the specified User-Agent string to perform the scan.

5. **Enable Verbose Output:**
   - **Description:** Show detailed information during the scan.
   - **Command:**
     ```bash
     whatweb -v example.com
     ```
   - **Example:**
     ```bash
     whatweb -v google.com
     ```
   - **Output:** Provides detailed output, including extra information about detected technologies.

6. **Scan for Specific Technologies:**
   - **Description:** Filter results to only show specific technologies.
   - **Command:**
     ```bash
     whatweb example.com --tech "CMS"
     ```
   - **Example:**
     ```bash
     whatweb google.com --tech "JavaScript"
     ```
   - **Output:** Filters the results to show only the specified technologies, such as CMS or JavaScript libraries.

7. **Scan with Custom Plugins:**
   - **Description:** Use custom plugins for technology detection.
   - **Command:**
     ```bash
     whatweb example.com --plugins /path/to/custom/plugins
     ```
   - **Example:**
     ```bash
     whatweb google.com --plugins /usr/share/whatweb/plugins/
     ```
   - **Output:** Uses the specified plugins for additional or custom technology detection.

8. **Show Help and Options:**
   - **Description:** Display available commands and options for `WhatWeb`.
   - **Command:**
     ```bash
     whatweb --help
     ```
   - **Example:**
     ```bash
     whatweb --help
     ```
   - **Output:** Lists available commands and options with descriptions.

### **Installation**

To install `WhatWeb`, you can typically use Ruby’s package manager `gem`:

```css
# Install WhatWeb using gem
gem install whatweb
```

### **Usage Notes**

- `WhatWeb` is effective for identifying technologies used by websites but may not always detect all technologies, especially if they are well-hidden or obfuscated.
- Custom plugins and user-agent strings can help tailor the scan to specific needs or bypass certain defenses.