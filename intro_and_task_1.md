
![Image](VUB-ETRO_RGB.jpg)

&nbsp;
# INTRODUCTION AND TASK 1
## OPERATING SYSTEMS AND SECURITY (OSSEC)
- **Student Name:** Zinar Mutlu
- **Student ID:** 0629829
- **Email:** zinar.mutlu@vub.be
- **Date:** 19/11/2024
&nbsp;

### 1. Introduction 
- Insert a brief introduction related to your explanations (e.g. what is swap memory, …)
&nbsp;
---
### 2. Task 1
- Task explanation with text and snapshots. Write Objective: Awareness about your hardware, software and vulnerabilities.
&nbsp;
---
#### 2.1 Exploring Personal Infrastructure
In this section, I will introduce my device(macOS 13-inch) specifications. Explore and check the characteristics (O.S., processor, memory,…) of your Personal Computers, Removable
Hardware, Network Equipment, Smart Phones and Tablets and any other equipment you will use for this course.
Tip: Check software such as Open Hardware Monitor
&nbsp;
![System Information](hardwareofmac.png)

##### Device specifications
1. Operating System: macOS Sequoia (v15.1)
2. Processor: Apple M1 (ARM-based SoC)
3. Total Number of Cores:	8 (4 performance and 4 efficiency)
4. Memory(RAM): 16 GB Unified Memory 
5. Storage capacity: 494,38 GB, APPLE SSD AP0512Q, 512 GB
6. Graphics: Apple M1 GPU, 8 cores, Retina Display (13.3-inch, 2560 x 1600 resolution)

##### Removable Hardware
1. Wi-Fi Card: Wi-Fi 6  
2. Bluetooth: Bluetooth 5.0
3. Ports:
    - Two Thunderbolt 3 (USB 4) ports
    - 3.5 mm headphone jack

#####  Network Equipment
1. Supported Wi-Fi standards: phy modes 802.11 a/b/g/n/ac/ax
2. Security protocols used WPA2/WPA3 Enterprise
3. Network speed: 400 Mbps

---

#### 2.2 Securing My Computer

##### 2.2.1. O.S. updates
O.S. updates contain new software that helps keep device current. Examples of updates include service packs, version upgrades, security updates, drivers, or other types of updates. Regularly updated macOS ensures the latest security patches and performance enhancements. Updates are automated via System Settings > General > Software Update.
![Software Updates](softwareupdates.png)
&nbsp;

##### 2.2.2. Firewall
A firewall decides which network traffic is allowed to pass through and which traffic is deemed dangerous. Essentially, it works by filtering out the good from the bad, or the trusted from the untrusted. Firewalls are intended to secure private networks and the endpoint devices within them, known as network hosts. Network hosts are devices that ‘talk’ with other hosts on the network. They send and receive between internal networks, as well as outbound and inbound between external networks. As it shown in the below picture the firewall is turned on and set up to prevent unauthorised applications, programs and services from accepting incoming connections. The macOS firewall is enabled to block unauthorized connections. Verified through System Settings > Network > Firewall.
![Firewall](firewall.png)
&nbsp;

##### 2.2.3. Antivirus
Apple operates a threat intelligence process to quickly identify and block malware. Malware defences are structured in three layers: 
- Prevent launch or execution of malware: App Store, or Gatekeeper combined with Notarisation
    ![Gatekeeper](gatekeeper.png)
&nbsp;
- Block malware from running on customer systems: Gatekeeper, Notarisation and XProtect
- Remediate malware that has executed: XProtect
    ![Xprotect](xprotect.png)
I tested this using the EICAR test file, but detection failed, suggesting either a misconfiguration or outdated definitions. Manual updates and configuration fixes were applied.
XProtect is active and functioning: The logs confirm that XProtect is performing scans and monitoring device activity as part of macOS's built-in malware protection. After activating Xprotect, the logs showed:
No critical errors: There are no warning or error messages, suggesting that XProtect is running as intended.
Device Activity Monitoring: The logs indicate that XProtect might be analyzing user activity or system events for potential threats.
![Xprotect](xprotectme.png)
&nbsp;
##### 2.2.4. Evaluate your security: EICAR test file, AMTSO Security Features Check,… (propose others!)
The [EICAR test](eicar.txt) file was developed by the European Institute for Computer Antivirus Research (EICAR) and Computer Antivirus Research Organization (CARO) to test the response of computer antivirus programs. Instead of using real malware, which could cause real damage, this test file allows people to test anti-virus software without having to use a real malware sample. So, this file is NOT actually malicious, but by industry-wide agreement this file is detected as malicious by mainstream products with antivirus functionality so that people can verify that their anti-malware product’s detection capability is configured correctly. 
![Eicar test](eicartest.png)
- EICAR Test File: Initially not detected; reconfigured XProtect and tested again.
- AMTSO Security Features Check: Verified active protection features such as download scanning and phishing protection.

---
### 2.3 Performance and Maintenance
By arranging startup applications, cleaning up the system, and implementing regular backups and disk maintenance, your MacBook will perform optimally while ensuring your data is secure. Unused startup applications were disabled via System Settings > General > Login Items, reducing boot time and improving startup performance. 
##### 2.3.1. Arrange Startup applications (e.g.: disable the ones you do not use at the startup)
Optimize system performance by reducing unnecessary startup applications. As a result, it improves boot times and reduces resource usage after startup.
![Startup Application](login.png)
##### 2.3.2. System cleanup the update files and disk cleaning (e.g. Ccleaner, Cleanup Windows,…)
- It improves system performance and more available storage. Storage cleaned through System Settings > Storage.
- Free up disk space and improve system responsiveness by removing unnecessary files.
![Storage](storage.png)
- I use CleanMyMac X to clear caches and old system logs.
![Ccleanup](cclean.png)
- Deleting large files by using filter files by size
![file size](filesize.png)
##### 2.3.3. System repair disk and Backup (e.g. Windows Backup, Google drive backup,…)
Ensure system integrity and protect data through regular maintenance and backups. I'm using third-party services like Google Drive or Dropbox to back up important documents and settings.
![backup](backup.png)
- From  Disk Utility > First Aid, I repair permissions and detect errors.
![repair](repair.png)
![disk utility](firstaid.png)

---

## 3. Conclusion
- Personal Comments: The task helped me understand my device’s capabilities and current vulnerabilities.
The XProtect test highlighted areas where macOS security could be better monitored or supplemented.
• What did I learn?
How to analyze hardware and network characteristics.
The importance of configuring built-in security tools like XProtect and Firewall.
Setting up and maintaining system backups efficiently.
• How much time did I need to do this exercise? Approximately 4 hours were spent completing this exercise, including research and testing security features.
• Any difficulties that I encountered to accomplish this exercise? EICAR test file was not detected initially, requiring additional configuration and troubleshooting.
Lack of detailed documentation on macOS security logs delayed evaluation.
• Suggestions to delete, keep or enhance this exercise for next year?
---

## 4. References
- [Apple Support: macOS Security Features](https://support.apple.com/en-gb/guide/security/sec469d47bd8/web)
- [AMTSO Security Features Check](https://www.amtso.org/feature-settings-check-download-of-malware/)
- [Firewall](https://www.kaspersky.com/resource-center/definitions/firewall)
