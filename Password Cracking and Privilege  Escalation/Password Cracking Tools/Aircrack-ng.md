Certainly! Here’s a detailed overview of the Aircrack-ng suite, including its common commands, options, and usage examples.

### **Aircrack-ng**

Aircrack-ng is a suite of tools for assessing WiFi network security. It includes tools for monitoring, attacking, testing, and cracking wireless networks.

#### **Common Tools and Commands**

1. **`airmon-ng`** - Start and stop monitor mode on wireless interfaces.

   - **Start Monitor Mode:**
     - **Description:** Put a wireless interface into monitor mode.
     - **Command:**
       ```bash
       airmon-ng start [interface]
       ```
     - **Example:**
       ```bash
       airmon-ng start wlan0
       ```
     - **Explanation:** 
       - `wlan0` is the interface to put into monitor mode.

   - **Stop Monitor Mode:**
     - **Description:** Stop monitor mode and revert to managed mode.
     - **Command:**
       ```bash
       airmon-ng stop [monitor_interface]
       ```
     - **Example:**
       ```bash
       airmon-ng stop wlan0mon
       ```

2. **`airodump-ng`** - Capture raw 802.11 frames.

   - **Capture Packets:**
     - **Description:** Capture packets from a specific channel or all channels.
     - **Command:**
       ```bash
       airodump-ng [options] [monitor_interface]
       ```
     - **Example:**
       ```bash
       airodump-ng wlan0mon
       ```

   - **Capture to a File:**
     - **Description:** Save captured packets to a file.
     - **Command:**
       ```bash
       airodump-ng -w [file_prefix] --bssid [AP_MAC] -c [channel] [monitor_interface]
       ```
     - **Example:**
       ```bash
       airodump-ng -w capture --bssid 00:11:22:33:44:55 -c 6 wlan0mon
       ```

   - **Explanation:**
     - `-w capture` specifies the prefix for the output files.
     - `--bssid` filters to capture packets from a specific AP.
     - `-c` specifies the channel to capture on.

3. **`aireplay-ng`** - Inject frames into a wireless network.

   - **Deauthenticate a Client:**
     - **Description:** Send deauthentication packets to a client or AP.
     - **Command:**
       ```bash
       aireplay-ng --deauth [count] -a [AP_MAC] -c [client_MAC] [monitor_interface]
       ```
     - **Example:**
       ```bash
       aireplay-ng --deauth 10 -a 00:11:22:33:44:55 -c 66:77:88:99:AA:BB wlan0mon
       ```

   - **Fake Authentication:**
     - **Description:** Attempt to authenticate to an AP.
     - **Command:**
       ```bash
       aireplay-ng --fakeauth [count] -a [AP_MAC] -h [client_MAC] [monitor_interface]
       ```
     - **Example:**
       ```bash
       aireplay-ng --fakeauth 0 -a 00:11:22:33:44:55 -h 66:77:88:99:AA:BB wlan0mon
       ```

4. **`aircrack-ng`** - Crack WEP and WPA/WPA2 keys.

   - **Crack WEP Key:**
     - **Description:** Crack WEP keys from captured packets.
     - **Command:**
       ```bash
       aircrack-ng -b [AP_MAC] [capture_file]
       ```
     - **Example:**
       ```bash
       aircrack-ng -b 00:11:22:33:44:55 capture-01.cap
       ```

   - **Crack WPA/WPA2 Key:**
     - **Description:** Crack WPA/WPA2 keys using a dictionary attack.
     - **Command:**
       ```bash
       aircrack-ng -w [wordlist] -b [AP_MAC] [capture_file]
       ```
     - **Example:**
       ```bash
       aircrack-ng -w passwords.txt -b 00:11:22:33:44:55 capture-01.cap
       ```

   - **Explanation:**
     - `-w` specifies the wordlist to use for cracking WPA/WPA2.

5. **`aircrack-ng` (Advanced WPA Cracking):**

   - **Crack WPA Handshake:**
     - **Description:** Crack WPA handshake from a capture file with a wordlist.
     - **Command:**
       ```bash
       aircrack-ng -w [wordlist] -b [AP_MAC] [capture_file]
       ```
     - **Example:**
       ```bash
       aircrack-ng -w rockyou.txt -b 00:11:22:33:44:55 capture-01.cap
       ```

6. **`airbase-ng`** - Create a fake access point.

   - **Start Fake AP:**
     - **Description:** Create a fake access point for testing or capturing.
     - **Command:**
       ```bash
       airbase-ng -e [AP_NAME] -c [channel] [monitor_interface]
       ```
     - **Example:**
       ```bash
       airbase-ng -e MyFakeAP -c 6 wlan0mon
       ```

   - **Explanation:**
     - `-e` specifies the name of the fake AP.
     - `-c` specifies the channel to use.

7. **`aircrack-ng` (Optional Parameters):**

   - **Verbose Output:**
     - **Description:** Show more detailed output during operations.
     - **Command:**
       ```bash
       aircrack-ng -v [options]
       ```
     - **Example:**
       ```bash
       aircrack-ng -v -w passwords.txt -b 00:11:22:33:44:55 capture-01.cap
       ```

   - **Debug Mode:**
     - **Description:** Enable debugging information for troubleshooting.
     - **Command:**
       ```bash
       aircrack-ng -d [options]
       ```
     - **Example:**
       ```bash
       aircrack-ng -d -w passwords.txt -b 00:11:22:33:44:55 capture-01.cap
       ```

#### **Summary of Aircrack-ng Options**

| **Tool**        | **Option**                       | **Description**                                | **Example**                                               |
|-----------------|----------------------------------|------------------------------------------------|-----------------------------------------------------------|
| `airmon-ng`     | `start [interface]`              | Start monitor mode on a wireless interface    | `airmon-ng start wlan0`                                  |
|                 | `stop [monitor_interface]`       | Stop monitor mode                              | `airmon-ng stop wlan0mon`                                |
| `airodump-ng`   | `-w [file_prefix]`               | Save captured packets to a file                | `airodump-ng -w capture wlan0mon`                        |
|                 | `--bssid [AP_MAC]`                | Filter by AP MAC address                       | `airodump-ng --bssid 00:11:22:33:44:55 wlan0mon`         |
|                 | `-c [channel]`                    | Specify channel                                | `airodump-ng -c 6 wlan0mon`                              |
| `aireplay-ng`   | `--deauth [count]`                | Send deauth packets                            | `aireplay-ng --deauth 10 -a 00:11:22:33:44:55 wlan0mon` |
|                 | `--fakeauth [count]`              | Send fake auth packets                         | `aireplay-ng --fakeauth 0 -a 00:11:22:33:44:55 wlan0mon` |
| `aircrack-ng`   | `-b [AP_MAC]`                     | Crack WEP key for a specific AP                | `aircrack-ng -b 00:11:22:33:44:55 capture-01.cap`       |
|                 | `-w [wordlist]`                   | Use a wordlist for cracking WPA/WPA2           | `aircrack-ng -w passwords.txt -b 00:11:22:33:44:55 capture-01.cap` |
| `airbase-ng`    | `-e [AP_NAME]`                   | Set the name for the fake AP                   | `airbase-ng -e MyFakeAP -c 6 wlan0mon`                   |
|                 | `-c [channel]`                    | Set the channel for the fake AP                | `airbase-ng -c 6 wlan0mon`                              |
| `aircrack-ng`   | `-v`                             | Verbose output                                 | `aircrack-ng -v -w passwords.txt -b 00:11:22:33:44:55 capture-01.cap` |
|                 | `-d`                             | Debug mode                                     | `aircrack-ng -d -w passwords.txt -b 00:11:22:33:44:55 capture-01.cap` |

---

Aircrack-ng provides a comprehensive suite of tools for assessing and testing WiFi network security, including packet capturing, injecting, and cracking functionalities.