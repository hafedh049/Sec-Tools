  - **Purpose**: Takes screenshots of web pages, RDP, and VNC services.
   - **Usage**: Useful for documenting web application attack surfaces or identifying interesting services visually.
   - **Syntax Examples**:
     - Screenshot capture:
       ```bash
       eyewitness --web --threads 5 --results ./output --no-prompt -f urls.txt
       ```
   - **When to Use**: Use it after an Nmap or web scan to visually document and check services for default login pages or interesting content.

`EyeWitness` is a tool for taking screenshots of websites and capturing web application banners, often used in penetration testing to gather information about web applications. It can capture screenshots of web pages and provide insights into web technologies and server configurations.

1. **Basic Website Screenshot Capture:**
   - **Description:** Capture screenshots of websites listed in a file.
   - **Command:**
     ```bash
     eyewitness -f urls.txt
     ```
   - **Example:**
     ```bash
     eyewitness -f websites.txt
     ```
   - **File `urls.txt` Content:**
     ```
     http://example.com
     http://google.com
     ```
   - **Output:** Captures screenshots of the websites listed in `urls.txt` and saves them in a directory named `EyeWitness`.

2. **Capture Screenshots and Banners:**
   - **Description:** Capture both screenshots and banners of websites.
   - **Command:**
     ```bash
     eyewitness -f urls.txt --web
     ```
   - **Example:**
     ```bash
     eyewitness -f websites.txt --web
     ```
   - **Output:** Captures screenshots and service banners of the websites listed.

3. **Use Specific Browser for Capture:**
   - **Description:** Specify a particular browser for taking screenshots.
   - **Command:**
     ```bash
     eyewitness -f urls.txt --browser chrome
     ```
   - **Example:**
     ```bash
     eyewitness -f websites.txt --browser firefox
     ```
   - **Output:** Uses the specified browser (e.g., Chrome or Firefox) to capture screenshots.

4. **Specify Output Directory:**
   - **Description:** Define a custom directory to save the screenshots and results.
   - **Command:**
     ```bash
     eyewitness -f urls.txt -o /path/to/output_directory
     ```
   - **Example:**
     ```bash
     eyewitness -f websites.txt -o /home/user/screenshots
     ```
   - **Output:** Saves screenshots and results to the specified directory.

5. **Enable Verbose Output:**
   - **Description:** Show detailed information during the capture process.
   - **Command:**
     ```bash
     eyewitness -f urls.txt -v
     ```
   - **Example:**
     ```bash
     eyewitness -f websites.txt -v
     ```
   - **Output:** Provides detailed output and progress information during the capture.

6. **Capture Screenshots with Custom User-Agent:**
   - **Description:** Use a custom User-Agent string for capturing screenshots.
   - **Command:**
     ```bash
     eyewitness -f urls.txt --user-agent "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36"
     ```
   - **Example:**
     ```bash
     eyewitness -f websites.txt --user-agent "MyCustomAgent/1.0"
     ```
   - **Output:** Uses the specified User-Agent string to capture screenshots.

7. **Capture Screenshots and Save HTML Source:**
   - **Description:** Capture screenshots and save the HTML source of the pages.
   - **Command:**
     ```bash
     eyewitness -f urls.txt --web --html
     ```
   - **Example:**
     ```bash
     eyewitness -f websites.txt --web --html
     ```
   - **Output:** Captures screenshots and saves the HTML source code of the pages.

8. **Show Help and Options:**
   - **Description:** Display available commands and options for `EyeWitness`.
   - **Command:**
     ```bash
     eyewitness --help
     ```
   - **Example:**
     ```bash
     eyewitness --help
     ```
   - **Output:** Lists available commands and options with descriptions.

### **Installation**

To install `EyeWitness`, you need to clone the repository and set it up. It requires Python and some additional dependencies:

```bash
# Clone the repository
git clone https://github.com/FortyNorthSecurity/EyeWitness.git
cd EyeWitness

# Install dependencies
pip install -r requirements.txt

# Make the script executable (optional)
chmod +x EyeWitness.py
```

### **Usage Notes**

- `EyeWitness` can generate a lot of data, so ensure you have enough disk space.
- The tool may require additional setup or configuration based on the environment and the types of websites being scanned.