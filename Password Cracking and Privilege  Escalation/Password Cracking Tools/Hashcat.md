Hashcat is a widely used password recovery tool that supports various hash algorithms and provides several modes of operation. Here’s a detailed overview of Hashcat’s options, arguments, and usage examples.

### **Hashcat**

#### **Common Arguments and Options**

1. **Basic Cracking Command:**
   - **Description:** Start a basic cracking session with a specified hash file and wordlist.
   - **Command:**
     ```bash
     hashcat [options] [hash_file] [wordlist_file]
     ```
   - **Example:**
     ```bash
     hashcat -m 0 -a 0 hashes.txt passwords.txt
     ```

   - **Explanation:**
     - `-m 0` specifies the hash type (MD5 in this case).
     - `-a 0` specifies the attack mode (straight mode using a wordlist).
     - `hashes.txt` contains the hashes to crack.
     - `passwords.txt` is the wordlist.

2. **Specify Hash Type:**
   - **Description:** Specify the type of hash to crack.
   - **Command:**
     ```bash
     hashcat -m [hash_type] [hash_file] [wordlist_file]
     ```
   - **Example:**
     ```bash
     hashcat -m 1000 hashes.txt passwords.txt
     ```

   - **Explanation:**
     - `-m 1000` specifies NTLM hash type.

3. **Attack Modes:**
   - **Description:** Choose different attack modes such as straight, combination, brute-force, or hybrid.
   - **Command:**
     ```bash
     hashcat -a [attack_mode] [hash_file] [wordlist_file]
     ```
   - **Example:**
     ```bash
     hashcat -a 3 hashes.txt ?a?a?a?a
     ```

   - **Explanation:**
     - `-a 3` specifies brute-force attack mode.
     - `?a?a?a?a` represents a 4-character password with all possible characters.

4. **Mask Attack:**
   - **Description:** Use a custom mask to specify the length and character set of passwords.
   - **Command:**
     ```bash
     hashcat -a 3 -m [hash_type] [hash_file] ?[charset1][charset2]...[charsetN]
     ```
   - **Example:**
     ```bash
     hashcat -a 3 -m 0 hashes.txt ?l?l?l?l
     ```

   - **Explanation:**
     - `?l` denotes a lowercase letter. `?l?l?l?l` represents a 4-character password with lowercase letters.

5. **Rules:**
   - **Description:** Apply rules to modify or expand wordlist entries.
   - **Command:**
     ```bash
     hashcat -a 0 -m [hash_type] [hash_file] [wordlist_file] -r [rules_file]
     ```
   - **Example:**
     ```bash
     hashcat -a 0 -m 0 hashes.txt passwords.txt -r rules/best64.rule
     ```

   - **Explanation:**
     - `-r rules/best64.rule` applies transformations from a specified rules file.

6. **Session Management:**
   - **Description:** Manage sessions to save and resume work.
   - **Command:**
     ```bash
     hashcat -o [output_file] --session=[session_name] [hash_file] [wordlist_file]
     ```
   - **Example:**
     ```bash
     hashcat -o cracked.txt --session=my_session hashes.txt passwords.txt
     ```

   - **Explanation:**
     - `--session=my_session` names the session for saving progress.

7. **Pause and Resume:**
   - **Description:** Pause and resume cracking sessions.
   - **Command:**
     ```bash
     hashcat --pause
     hashcat --resume
     ```
   - **Example:**
     ```bash
     hashcat --pause
     hashcat --resume
     ```

   - **Explanation:**
     - `--pause` stops the cracking session.
     - `--resume` continues from where it left off.

8. **Benchmarking:**
   - **Description:** Run a performance benchmark to test the speed of Hashcat.
   - **Command:**
     ```bash
     hashcat --benchmark
     ```
   - **Example:**
     ```bash
     hashcat --benchmark
     ```

   - **Explanation:**
     - `--benchmark` tests the performance of Hashcat for various algorithms.

9. **Help and Version Information:**
   - **Description:** Display help or version information for Hashcat.
   - **Command:**
     ```bash
     hashcat --help
     hashcat --version
     ```
   - **Example:**
     ```bash
     hashcat --help
     hashcat --version
     ```

   - **Explanation:**
     - `--help` provides usage information.
     - `--version` shows the version of Hashcat.

10. **Restore Cracking Session:**
    - **Description:** Restore a previously saved cracking session.
    - **Command:**
      ```bash
      hashcat --restore --session=[session_name]
      ```
    - **Example:**
      ```bash
      hashcat --restore --session=my_session
      ```

    - **Explanation:**
      - `--restore` resumes a saved session with the specified name.

#### **Summary of Hashcat Options**

| **Option**                     | **Description**                              | **Example**                                             |
|--------------------------------|----------------------------------------------|---------------------------------------------------------|
| `-m [hash_type]`               | Specify hash type                           | `hashcat -m 0 hashes.txt passwords.txt`                |
| `-a [attack_mode]`             | Specify attack mode                         | `hashcat -a 3 hashes.txt ?a?a?a?a`                     |
| `-r [rules_file]`              | Apply rules to wordlist                     | `hashcat -a 0 -r rules/best64.rule hashes.txt passwords.txt` |
| `--session=[session_name]`     | Specify a session name                      | `hashcat --session=my_session hashes.txt passwords.txt`|
| `--pause`                      | Pause a cracking session                    | `hashcat --pause`                                      |
| `--resume`                     | Resume a paused session                     | `hashcat --resume`                                     |
| `--benchmark`                  | Run performance benchmarks                  | `hashcat --benchmark`                                  |
| `--help`                       | Display help information                    | `hashcat --help`                                       |
| `--version`                    | Show version information                    | `hashcat --version`                                    |
| `--restore`                    | Restore a previously saved session          | `hashcat --restore --session=my_session`               |

---

Hashcat is a powerful and flexible tool for password cracking, offering various modes and options to handle different cracking scenarios efficiently.