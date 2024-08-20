Here’s a detailed overview of Medusa, including its options, arguments, and examples of usage.

### **Medusa**

Medusa is a speedy, parallel, and modular login brute-forcer for networks and services. It supports various protocols and can perform brute-force attacks against numerous services.

#### **Common Options and Arguments**

1. **Basic Usage:**
   - **Description:** Run a basic brute-force attack using Medusa.
   - **Command:**
     ```bash
     medusa -h <target> -u <username> -P <password_list> -M <module>
     ```
   - **Example:**
     ```bash
     medusa -h 192.168.1.100 -u admin -P /path/to/passwords.txt -M ssh
     ```
   - **Explanation:** 
     - `-h`: Target host or IP.
     - `-u`: Username to brute-force.
     - `-P`: Path to the password list.
     - `-M`: Module to use (e.g., `ssh`, `ftp`, etc.).

2. **Specify a Port:**
   - **Description:** Define the port number to connect to on the target service.
   - **Command:**
     ```bash
     medusa -h <target> -u <username> -P <password_list> -M <module> -p <port>
     ```
   - **Example:**
     ```bash
     medusa -h 192.168.1.100 -u admin -P /path/to/passwords.txt -M ssh -p 22
     ```
   - **Explanation:** 
     - `-p`: Port number to use.

3. **Specify a Number of Threads:**
   - **Description:** Set the number of concurrent threads to speed up the attack.
   - **Command:**
     ```bash
     medusa -h <target> -u <username> -P <password_list> -M <module> -t <threads>
     ```
   - **Example:**
     ```bash
     medusa -h 192.168.1.100 -u admin -P /path/to/passwords.txt -M ssh -t 16
     ```
   - **Explanation:** 
     - `-t`: Number of threads to use.

4. **Specify a Timeout:**
   - **Description:** Set a timeout for each connection attempt.
   - **Command:**
     ```bash
     medusa -h <target> -u <username> -P <password_list> -M <module> -T <timeout>
     ```
   - **Example:**
     ```bash
     medusa -h 192.168.1.100 -u admin -P /path/to/passwords.txt -M ssh -T 30
     ```
   - **Explanation:** 
     - `-T`: Timeout in seconds.

5. **Specify a Username List:**
   - **Description:** Use a list of usernames instead of a single username.
   - **Command:**
     ```bash
     medusa -h <target> -U <username_list> -P <password_list> -M <module>
     ```
   - **Example:**
     ```bash
     medusa -h 192.168.1.100 -U /path/to/usernames.txt -P /path/to/passwords.txt -M ssh
     ```
   - **Explanation:** 
     - `-U`: Path to a file containing usernames.

6. **Use SSL/TLS:**
   - **Description:** Enable SSL/TLS for connections to services that support it.
   - **Command:**
     ```bash
     medusa -h <target> -u <username> -P <password_list> -M <module> -s <ssl>
     ```
   - **Example:**
     ```bash
     medusa -h 192.168.1.100 -u admin -P /path/to/passwords.txt -M pop3 -s ssl
     ```
   - **Explanation:** 
     - `-s`: Enable SSL/TLS (`ssl`).

7. **Output Results to a File:**
   - **Description:** Save the results of the brute-force attack to a file.
   - **Command:**
     ```bash
     medusa -h <target> -u <username> -P <password_list> -M <module> -O <output_file>
     ```
   - **Example:**
     ```bash
     medusa -h 192.168.1.100 -u admin -P /path/to/passwords.txt -M ssh -O results.txt
     ```
   - **Explanation:** 
     - `-O`: Output file to save results.

8. **Specify a List of Targets:**
   - **Description:** Use a list of target hosts instead of a single target.
   - **Command:**
     ```bash
     medusa -h <target_list> -u <username> -P <password_list> -M <module>
     ```
   - **Example:**
     ```bash
     medusa -h /path/to/targets.txt -u admin -P /path/to/passwords.txt -M ssh
     ```
   - **Explanation:** 
     - `-h`: Path to a file containing a list of targets.

#### **Summary of Medusa Options**

| **Option**        | **Description**                                        | **Example**                                                |
|-------------------|--------------------------------------------------------|------------------------------------------------------------|
| `-h <target>`     | Target host or IP address                             | `-h 192.168.1.100`                                        |
| `-u <username>`   | Username for brute-force                              | `-u admin`                                                 |
| `-U <username_list>` | List of usernames to use                             | `-U /path/to/usernames.txt`                               |
| `-P <password_list>` | Path to a password list                             | `-P /path/to/passwords.txt`                               |
| `-M <module>`     | Service module to use (e.g., `ssh`, `ftp`, `http`)    | `-M ssh`                                                   |
| `-p <port>`       | Port number to connect to                             | `-p 22`                                                   |
| `-t <threads>`    | Number of concurrent threads                          | `-t 16`                                                   |
| `-T <timeout>`    | Timeout for each connection attempt                   | `-T 30`                                                   |
| `-s <ssl>`        | Enable SSL/TLS for connections                        | `-s ssl`                                                  |
| `-O <output_file>` | Save results to a file                               | `-O results.txt`                                         |
| `-h <target_list>` | List of target hosts                                 | `-h /path/to/targets.txt`                                |

**Medusa** is a powerful tool for performing brute-force attacks against various services and protocols, with support for high concurrency and various configurations to optimize attacks.