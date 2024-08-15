  - **Purpose**: Search engine for Internet-connected devices.
   - **Usage**: Find public-facing devices and services (cameras, servers, IoT devices).
   - **Syntax Examples**:
     - Via web interface (or API) at https://www.shodan.io/
   - **When to Use**: Use it to find publicly exposed services and devices, ideal for passive reconnaissance.

`shodan` is a command-line interface (CLI) for interacting with the Shodan search engine, which provides information about internet-connected devices. Below are the key commands and options for using `shodan`.

1. **Search for Devices:**
   - **Description:** Search Shodan for devices matching a query.
   - **Command:**
     ```bash
     shodan search "apache"
     ```
   - **Example:**
     ```bash
     shodan search "port:80 country:US"
     ```
   - **Output:** Lists devices that match the search criteria.

2. **Retrieve Device Information by IP:**
   - **Description:** Get detailed information about a specific IP address.
   - **Command:**
     ```bash
     shodan host 8.8.8.8
     ```
   - **Example:**
     ```bash
     shodan host 192.168.1.1
     ```
   - **Output:** Provides details such as open ports, services, and metadata for the specified IP address.

3. **Show Shodan Account Info:**
   - **Description:** Display information about the current Shodan account.
   - **Command:**
     ```bash
     shodan info
     ```
   - **Example:**
     ```bash
     shodan info
     ```
   - **Output:** Shows account details including the number of API queries remaining and account type.

4. **Perform a Scan:**
   - **Description:** Trigger a scan for a specific IP range (requires a Shodan API key and proper permissions).
   - **Command:**
     ```bash
     shodan scan submit 192.168.1.0/24
     ```
   - **Example:**
     ```bash
     shodan scan submit 10.0.0.0/8
     ```
   - **Output:** Submits a scan job for the specified IP range.

5. **List All Scans:**
   - **Description:** Retrieve a list of all scan jobs.
   - **Command:**
     ```bash
     shodan scan list
     ```
   - **Example:**
     ```bash
     shodan scan list
     ```
   - **Output:** Displays information about all scan jobs, including their status.

6. **Show Scan Details:**
   - **Description:** Get details of a specific scan job.
   - **Command:**
     ```bash
     shodan scan info <scan-id>
     ```
   - **Example:**
     ```bash
     shodan scan info 1234567890
     ```
   - **Output:** Provides details about the specified scan job, including its progress and results.

7. **Export Search Results:**
   - **Description:** Export search results to a file.
   - **Command:**
     ```bash
     shodan search "apache" --fields ip_str,port --limit 1000 > results.csv
     ```
   - **Example:**
     ```bash
     shodan search "port:22" --fields ip_str,port,org --limit 500 > ssh_results.csv
     ```
   - **Output:** Saves the search results in a CSV file.

8. **Get Alerts:**
   - **Description:** List all Shodan alerts.
   - **Command:**
     ```bash
     shodan alert list
     ```
   - **Example:**
     ```bash
     shodan alert list
     ```
   - **Output:** Displays a list of configured alerts.

9. **Create an Alert:**
   - **Description:** Set up a new Shodan alert.
   - **Command:**
     ```bash
     shodan alert create "port:80"
     ```
   - **Example:**
     ```bash
     shodan alert create "country:US"
     ```
   - **Output:** Creates a new alert based on the specified criteria.

10. **Show Help and Options:**
    - **Description:** Display available commands and options.
    - **Command:**
      ```bash
      shodan --help
      ```
    - **Example:**
      ```bash
      shodan --help
      ```
    - **Output:** Lists available commands and options with descriptions.

### **Installation**

To use the `shodan` CLI, you need to install it via Python's package manager `pip`:

```bash
pip install shodan
```

### **Usage Notes**

- You need a Shodan API key to perform some operations like scanning and accessing detailed search results.
- The `shodan` CLI tool is a powerful way to interact with Shodan’s data, but be aware of the rate limits and API usage restrictions associated with your account.

