Here's an overview of **Escalate**, a tool designed for privilege escalation on Unix-like systems, including its options, arguments, and usage examples.

### **Escalate**

**Escalate** is a tool for identifying and exploiting privilege escalation vulnerabilities on Unix-like systems. It helps find misconfigurations and potential security issues that can be exploited to gain elevated privileges.

#### **Common Options and Arguments**

1. **Basic Execution:**
   - **Description:** Run Escalate with default settings to perform a standard privilege escalation check.
   - **Command:**
     ```bash
     ./escalate.sh
     ```
   - **Example:**
     - Simply running the script will perform a comprehensive check for privilege escalation vulnerabilities.

2. **Specify Output Format:**
   - **Description:** Define the output format for the results (e.g., text, JSON).
   - **Command:**
     ```bash
     ./escalate.sh -o <format>
     ```
   - **Example:**
     ```bash
     ./escalate.sh -o json
     ```
   - **Explanation:**
     - `-o <format>`: Output format. Options include `text` and `json`.

3. **Run Specific Checks:**
   - **Description:** Execute only specific checks or categories.
   - **Command:**
     ```bash
     ./escalate.sh -c <check>
     ```
   - **Example:**
     ```bash
     ./escalate.sh -c kernel
     ```
   - **Explanation:**
     - `-c <check>`: Run only the specified check. Possible values include `kernel`, `services`, `suid`, etc.

4. **Enable Verbose Mode:**
   - **Description:** Increase the verbosity of the output to provide more detailed information.
   - **Command:**
     ```bash
     ./escalate.sh -v
     ```
   - **Example:**
     - Running with `-v` will show more detailed output during execution.

5. **Run in Non-Interactive Mode:**
   - **Description:** Run the script in non-interactive mode, useful for automated environments.
   - **Command:**
     ```bash
     ./escalate.sh -n
     ```
   - **Example:**
     - Execute the script without interactive prompts or user input.

6. **Specify Custom Search Paths:**
   - **Description:** Customize search paths for files and configurations.
   - **Command:**
     ```bash
     ./escalate.sh -p <path>
     ```
   - **Example:**
     ```bash
     ./escalate.sh -p /usr/local/bin
     ```
   - **Explanation:**
     - `-p <path>`: Path to additional directories or files to include in the scan.

7. **Save Output to File:**
   - **Description:** Redirect the output to a file for later review.
   - **Command:**
     ```bash
     ./escalate.sh -o <output_file>
     ```
   - **Example:**
     ```bash
     ./escalate.sh -o escalate_results.txt
     ```
   - **Explanation:**
     - `-o <output_file>`: File path where the results will be saved.

8. **Specify the User to Run Checks As:**
   - **Description:** Run the checks as a specific user.
   - **Command:**
     ```bash
     su - <user> -c "./escalate.sh"
     ```
   - **Example:**
     ```bash
     su - testuser -c "./escalate.sh"
     ```
   - **Explanation:**
     - `su - <user> -c "<command>"`: Execute the script as the specified user.

#### **Summary of Escalate Options**

| **Option**               | **Description**                                           | **Example**                                    |
|--------------------------|-----------------------------------------------------------|------------------------------------------------|
| `-o <format>`            | Output format (text, json)                               | `-o json`                                     |
| `-c <check>`             | Run specific check/category                             | `-c kernel`                                   |
| `-v`                     | Verbose mode for detailed output                        | `-v`                                          |
| `-n`                     | Non-interactive mode                                    | `-n`                                          |
| `-p <path>`              | Custom search paths                                     | `-p /usr/local/bin`                           |
| `-o <output_file>`       | Save output to file                                      | `-o escalate_results.txt`                      |
| `su - <user> -c "<command>"` | Run checks as a specific user                           | `su - testuser -c "./escalate.sh"`            |

**Escalate** is a powerful tool for identifying privilege escalation vectors on Unix-like systems, helping to detect misconfigurations and vulnerabilities that could be exploited to gain higher privileges.