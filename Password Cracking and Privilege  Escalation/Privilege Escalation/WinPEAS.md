Here's an overview of **WinPEAS**, a Windows privilege escalation script, including its options, arguments, and usage examples.

### **WinPEAS (Windows Privilege Escalation Awesome Script)**

WinPEAS is a script designed to help identify potential privilege escalation vectors on Windows systems. It searches for configuration issues, misconfigurations, and vulnerabilities that could be exploited to gain elevated privileges.

#### **Common Options and Arguments**

1. **Basic Execution:**
   - **Description:** Run WinPEAS with default settings to perform a standard privilege escalation check.
   - **Command:**
     ```cmd
     .\winPEAS.bat
     ```
   - **Example:**
     - Simply running the script will perform a comprehensive check of the system’s security posture.

2. **Specify Output Format:**
   - **Description:** Define the output format for the results (e.g., JSON, HTML).
   - **Command:**
     ```cmd
     .\winPEAS.bat -o <format>
     ```
   - **Example:**
     ```cmd
     .\winPEAS.bat -o json
     ```
   - **Explanation:**
     - `-o <format>`: Output format. Options include `json`, `html`, `xml`, or `txt`.

3. **Run Specific Checks:**
   - **Description:** Execute only specific checks or categories.
   - **Command:**
     ```cmd
     .\winPEAS.bat -c <check>
     ```
   - **Example:**
     ```cmd
     .\winPEAS.bat -c services
     ```
   - **Explanation:**
     - `-c <check>`: Run only the specified check. Possible values include `services`, `scheduled_tasks`, `shares`, etc.

4. **Enable Verbose Mode:**
   - **Description:** Increase the verbosity of the output to provide more detailed information.
   - **Command:**
     ```cmd
     .\winPEAS.bat -v
     ```
   - **Example:**
     - Running with `-v` will show more detailed output during execution.

5. **Run in Non-Interactive Mode:**
   - **Description:** Run the script in non-interactive mode, which is useful for automated environments.
   - **Command:**
     ```cmd
     .\winPEAS.bat -noninteractive
     ```
   - **Example:**
     - Execute the script without interactive prompts or user input.

6. **Specify Custom Search Paths:**
   - **Description:** Customize search paths for files and configurations.
   - **Command:**
     ```cmd
     .\winPEAS.bat -p <path>
     ```
   - **Example:**
     ```cmd
     .\winPEAS.bat -p C:\Custom\Path
     ```
   - **Explanation:**
     - `-p <path>`: Path to additional directories or files to include in the scan.

7. **Save Output to File:**
   - **Description:** Redirect the output to a file for later review.
   - **Command:**
     ```cmd
     .\winPEAS.bat -o <output_file>
     ```
   - **Example:**
     ```cmd
     .\winPEAS.bat -o winpeas_results.txt
     ```
   - **Explanation:**
     - `-o <output_file>`: File path where the results will be saved.

8. **Specify the User to Run Checks As:**
   - **Description:** Run the checks as a specific user.
   - **Command:**
     ```cmd
     runas /user:<user> .\winPEAS.bat
     ```
   - **Example:**
     ```cmd
     runas /user:testuser .\winPEAS.bat
     ```
   - **Explanation:**
     - `runas /user:<user>`: Execute the script as the specified user.

#### **Summary of WinPEAS Options**

| **Option**               | **Description**                                           | **Example**                                    |
|--------------------------|-----------------------------------------------------------|------------------------------------------------|
| `-o <format>`            | Output format (json, html, xml, txt)                     | `-o json`                                     |
| `-c <check>`             | Run specific check/category                             | `-c services`                                 |
| `-v`                     | Verbose mode for detailed output                        | `-v`                                          |
| `-noninteractive`        | Run script in non-interactive mode                       | `-noninteractive`                             |
| `-p <path>`              | Custom search paths                                     | `-p C:\Custom\Path`                           |
| `-o <output_file>`       | Save output to file                                      | `-o winpeas_results.txt`                      |
| `runas /user:<user>`     | Run checks as a specific user                            | `runas /user:testuser .\winPEAS.bat`          |

**WinPEAS** is a useful tool for assessing privilege escalation paths on Windows systems. It provides detailed information about system misconfigurations and vulnerabilities that could be exploited to gain higher privileges.