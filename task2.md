![Image](pictures/VUB-ETRO_RGB.jpg)

&nbsp;  
# TASK 2: Process Explorer and Swap Memory on a macOS System  
## OPERATING SYSTEMS AND SECURITY (OSSEC)  

- **Student Name:** Zinar Mutlu  
- **Student ID:** 0629829  
- **Email:** zinar.mutlu@vub.be  
- **Date:** 08/02/2025  

&nbsp;  

## Introduction  
The objective of this task is to examine active processes and memory management on a macOS system. This includes an overview of tools for process monitoring, network connection tracking, and swap memory management. Instead of Windows tools like Task Manager and Sysinternals Utilities, I will use macOS-specific tools such as **Activity Monitor**, `top`, and `htop` to explore active processes and manage swap memory efficiently. The goal is to understand how macOS handles system resources and how users can analyze and optimize system performance.  

&nbsp;  

---

## 1. Exploring Active Processes in macOS  

Activity Monitor is a built-in macOS utility that provides a graphical interface for monitoring system performance and managing processes. For more detailed system monitoring and resource management, macOS provides command-line tools like `top` and `htop`.  

- **`top`**: A built-in macOS tool for real-time process monitoring.  
- **`htop`**: An enhanced version of `top`, offering an interactive and user-friendly interface.  

&nbsp;  

### 1.1 Activity Monitor (GUI Tool)  
- Access via **Applications → Utilities → Activity Monitor** or Spotlight (`Cmd + Space`, then search for "Activity Monitor"). 
**Activity Monitor**
![Activity Monitor](pictures2/cpu.png)
![Activity Monitor](pictures2/activitmonitor.png) 
- Displays CPU, Memory, Energy, Disk, and Network usage for each running process. 
**CPU Usage**
 ![Activity Monitor](pictures2/cpuusage.png)
**Memory**
![Activity Monitor](pictures2/memory.png)
**Energy**
![Activity Monitor](pictures2/energy.png)
**Disk**   
![Activity Monitor](pictures2/disk.png)
**Netowrk**
![Activity Monitor](pictures2/network.png)

- Allows users to **force quit** applications or processes consuming excessive resources.  
![Activity Monitor](pictures2/forcequit.png)
- Users can **sort processes** based on resource consumption.  
![Activity Monitor](pictures2/sensorsshort.png)
- Provides a **real-time graphical representation** of system activity.  
![Activity Monitor](pictures2/cpushort.png)
![Activity Monitor](pictures2/cpuhistory.png)

&nbsp;  

### 1.2 Terminal-Based Process Monitoring: `top` Command  
Run in Terminal:  `top`
![Activity Monitor](pictures2/top.png)
- Displays real-time CPU and memory usage of running processes.
- Lists a list of active processes sorted by CPU usage.
- Shows memory consumption, process ID (PID), and execution time.
- Updates in real-time, providing dynamic process tracking.
![Activity Monitor](pictures2/topdetails.png)

&nbsp;  
### 1.3. Monitoring Network Connections
Tracking network activity is essential for identifying unauthorized connections and monitoring resource usage. Below are alternatives to **netstat** for macOS.
#### 1.3.1 `nettop` (Real-time Network Monitoring)
Run in Terminal:  `nettop`
- Displays active network connections in real-time.
![Activity Monitor](pictures2/nettop.png)
![Activity Monitor](pictures2/nettopdetails.png)
![Activity Monitor](pictures2/network.png)
#### 1.3.2 `lsof` (List Open Network Connections)
Run in Terminal:  `sudo lsof -i -P`

Lists processes utilizing network connections, including ports and protocols.
![Activity Monitor](pictures2/lsof.png)
#### 1.3.3 `ifconfig` (Check Network Interfaces)
Run in Terminal:  `ifconfig`
![Activity Monitor](pictures2/ipconfig.png)
Displays details on active network interfaces, IP addresses, and data transmission.
![Activity Monitor](pictures2/ipadd.png)
&nbsp;  

---
## 2. Checking and expanding your SWAP memory
macOS dynamically manages swap memory, but users can monitor and adjust its behavior. Swap memory (virtual memory) is a portion of disk storage that macOS uses as an **extension of RAM** when physical memory is full. When the system runs out of RAM, inactive memory pages are moved to the swap space to **free up RAM for active processes**, preventing system slowdowns and application crashes.
&nbsp;  

### 2.1 Checking Current Swap Usage
To check swap memory usage, run:
`sysctl vm.swapusage`
![Activity Monitor](pictures2/swapusage.png)
&nbsp; 
### 2.2 Checking System Memory Usage
Run: `vm_stat`
- This command provides details on **free memory, inactive memory, and swap usage.**
![Activity Monitor](pictures2/vm_stat.png)
&nbsp; 
### 2.3 Adjusting Swap Memory
macOS dynamically manages swap based on system requirements, but users can **enable or disable** it manually but it isn't recommended for most users. On macOS, swap memory works differently than on Windows or Linux. Virtual memory in macOS involves the use of:

- **Memory Compression**: Compresses inactive memory pages' contents, reducing the need for swapping to disk and improving overall system performance.
- **Swap Space**: Serves as a last resort when other memory management techniques cannot handle memory demands.

**Disable/Enable Swap (Not Recommended)** 

`sudo launchctl unload -w /System/Library/LaunchDaemons/com.apple.dynamic_pager.plist`

- macOS does not allow disabling swap this way in newer versions. It gives `Boot-out failed: 5: Input/output error`
- In this case, we use `sudo purge` command to free up inactive memory and close unnecessary applications.

- Swap memory usage can be displayed in the Activity Monitor under Memory Usage:
![Activity Monitor](pictures2/swapused.png)
The Swap Used value shows how much swap memory is currently being used.
&nbsp;  
---

## Conclusion
This report provides an overview of how macOS handles **process monitoring, memory management, and network connections.** By using built-in and third-party tools like **Activity Monitor, `top`, `nettop`, and `sysctl`,** users can efficiently manage system resources. Proper monitoring helps in **optimizing performance and ensuring system stability.** 

&nbsp;
---

## References
- Apple Support Documentation: https://support.apple.com
- macOS Terminal Commands: https://ss64.com/osx/

