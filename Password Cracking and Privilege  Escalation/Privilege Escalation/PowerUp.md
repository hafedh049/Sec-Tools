Here is an overview of **PowerUp**, a PowerShell script designed for Windows privilege escalation enumeration. It helps in identifying potential privilege escalation vectors and misconfigurations on Windows systems.

### **PowerUp**

**PowerUp** is a PowerShell script used to identify privilege escalation opportunities on Windows systems. It checks for various common misconfigurations and vulnerabilities that might allow an attacker to escalate privileges.

#### **Common Options and Arguments**

1. **Basic Execution:**
   - **Description:** Run PowerUp with default settings to perform standard privilege escalation checks.
   - **Command:**
     ```powershell
     .\PowerUp.ps1
     ```
   - **Example:**
     - Simply executing the script will start the enumeration process with default checks.

2. **Run Specific Checks:**
   - **Description:** Specify which checks to perform.
   - **Command:**
     ```powershell
     .\PowerUp.ps1 -Check <check_name>
     ```
   - **Example:**
     ```powershell
     .\PowerUp.ps1 -Check LocalAdmin
     ```
   - **Explanation:**
     - `-Check <check_name>`: Run only the specified check. Possible values include `LocalAdmin`, `ScheduledTasks`, `Services`, etc.

3. **Generate Detailed Output:**
   - **Description:** Increase verbosity for detailed output and information.
   - **Command:**
     ```powershell
     .\PowerUp.ps1 -Verbose
     ```
   - **Example:**
     - Use `-Verbose` to get detailed information during the script execution.

4. **Save Output to File:**
   - **Description:** Redirect the results to a file for later analysis.
   - **Command:**
     ```powershell
     .\PowerUp.ps1 -OutputFile <path>
     ```
   - **Example:**
     ```powershell
     .\PowerUp.ps1 -OutputFile C:\PowerUpResults.txt
     ```
   - **Explanation:**
     - `-OutputFile <path>`: Specify the path to save the output file.

5. **Specify Output Format:**
   - **Description:** Choose the format for the output (e.g., text, XML).
   - **Command:**
     ```powershell
     .\PowerUp.ps1 -OutputFormat <format>
     ```
   - **Example:**
     ```powershell
     .\PowerUp.ps1 -OutputFormat xml
     ```
   - **Explanation:**
     - `-OutputFormat <format>`: Options include `text` and `xml`.

6. **Run in Non-Interactive Mode:**
   - **Description:** Execute the script in non-interactive mode, useful for automation.
   - **Command:**
     ```powershell
     .\PowerUp.ps1 -NonInteractive
     ```
   - **Example:**
     - Use `-NonInteractive` to run the script without user prompts.

7. **Include Additional Modules:**
   - **Description:** Load additional PowerShell modules if required.
   - **Command:**
     ```powershell
     .\PowerUp.ps1 -Modules <module_names>
     ```
   - **Example:**
     ```powershell
     .\PowerUp.ps1 -Modules PSReadLine, ScheduledTasks
     ```
   - **Explanation:**
     - `-Modules <module_names>`: List of additional modules to include.

8. **Run as a Specific User:**
   - **Description:** Execute the script as a different user.
   - **Command:**
     ```powershell
     Start-Process powershell -ArgumentList ".\PowerUp.ps1" -Credential <username>
     ```
   - **Example:**
     ```powershell
     Start-Process powershell -ArgumentList ".\PowerUp.ps1" -Credential testuser
     ```
   - **Explanation:**
     - `-Credential <username>`: Run the script with the specified user's credentials.

#### **Summary of PowerUp Options**

| **Option**               | **Description**                                             | **Example**                                    |
|--------------------------|-------------------------------------------------------------|------------------------------------------------|
| `-Check <check_name>`    | Run specific check or category                             | `-Check LocalAdmin`                            |
| `-Verbose`               | Detailed output                                            | `-Verbose`                                     |
| `-OutputFile <path>`     | Save output to file                                        | `-OutputFile C:\PowerUpResults.txt`            |
| `-OutputFormat <format>` | Output format (text, xml)                                  | `-OutputFormat xml`                            |
| `-NonInteractive`        | Run in non-interactive mode                                | `-NonInteractive`                              |
| `-Modules <module_names>`| Load additional PowerShell modules                         | `-Modules PSReadLine, ScheduledTasks`          |
| `Start-Process -Credential <username>` | Run as a different user                       | `Start-Process powershell -Credential testuser`|

**PowerUp** helps in detecting potential privilege escalation opportunities by enumerating various system settings and configurations that might be leveraged to gain higher privileges. It is an essential tool for security professionals and penetration testers working with Windows systems.