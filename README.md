# 💀HyperDOS💀

## 📜Description
This tool is designed for network security research and stress testing purposes. It allows cybersecurity professionals and researchers to analyze network robustness by simulating different types of high-traffic scenarios. The tool provides various attack types, including TCP SYN flood, UDP flood, ICMP flood, and HTTP flood, enabling users to test their infrastructure's resilience against potential DDoS threats.

> [!NOTE]
> ***This tool is ONLY for demonstrate how network systems and services may be stressed under load and to help with understanding network performance. Unauthorized or malicious use of this tool can lead to legal consequences, including criminal charges.***

## 🔑Features
✔️ Multiple Attack Modes:  
- TCP SYN Flood: Simulates SYN requests to overload a target server.  
- UDP Flood: Sends high-volume UDP packets to the target.  
- ICMP Flood: Uses ICMP packets to flood a network.  
- HTTP Flood: Sends HTTP GET requests to overwhelm web applications.  
✔️ Multi-threaded Execution: Efficiently manages large-scale network traffic simulation.  
✔️ Customizable Parameters: Users can define packet sizes, number of threads, attack duration, and request rates.  
✔️ Logging & Output Formatting: Displays real-time attack statistics with color-coded logs.  
✔️ IP Spoofing: Generates random source IP addresses for simulating distributed traffic.  
✔️ Error Handling & Validation: Ensures valid inputs, domain resolution, and network stability.  

## 🚀Step-by-Step Guide in Linux Terminal !

Step 1: Update & upgrade your system  
>sudo apt update  

>sudo apt upgrade  

Step 2: install Dependencies  
>sudo apt install python3-fake-useragent  

>sudo apt install python3-aiohttp  

>sudo apt install python3-scapy  

>sudo apt install python3-requests  

Step 3: Clone the repository  
>git clone https://github.com/The-Real-Virus/HyperDOS.git  

Step 4: Go to the Tool Directory where u clone it  
>cd HyperDOS  

Step 5: After Completing the process now u can run script  
>sudo python3 hyperdos.py  

> [!IMPORTANT]
> **Root privileges are required to execute the tool.**

## 💡Attack Modes !
**[TCP](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) SYN Flood:** A TCP SYN flood attack exploits the TCP handshake process. It sends a barrage of SYN requests to the target, overwhelming its ability to respond and establish legitimate connections.

**[ICMP](https://en.wikipedia.org/wiki/Internet_Control_Message_Protocol) Flood (Ping of Death):** An ICMP flood attack sends a high volume of ICMP Echo Request (ping) packets to the target, aiming to overwhelm its network bandwidth and processing power.

**[UDP](https://en.wikipedia.org/wiki/User_Datagram_Protocol) Flood:** A UDP flood attack involves sending a large number of UDP packets to random ports on the target system, causing it to become overwhelmed as it processes the packets and replies with ICMP Destination Unreachable messages.

**[HTTP](https://en.wikipedia.org/wiki/HTTP) Flood:** An HTTP flood attack aims to overload a server with HTTP requests, exhausting its resources and potentially leading to denial of service.

## 🤝Working Nature !
* Let's take UDP Flood as an example.

* A UDP flood attack can be initiated by sending a large number of **UDP packets** to random ports on a remote host. As a result, the distant host will:

    * Check for the application listening at that port;
    * See that no application listens at that port;
    * Reply with an ICMP Destination Unreachable packet.

* Thus, for a large number of UDP packets, the victimized system will be forced into sending many ICMP packets, eventually leading it to be unreachable by other clients. Net Strike can also spoof the IP address of the UDP packets, ensuring that the excessive ICMP return packets do not reach you, and anonymizing your network location.

* **However**, unlike other types of attacks, HTTP Flood works in a somewhat different manner.

* An HTTP flood attack aims to overload a server with **HTTP requests**. This type of attack can take various forms, such as GET or POST requests. As a result, the target server will:

   * Receive an overwhelming number of requests;
   * Attempt to process each request as a legitimate user;
   * Exhaust its resources (CPU, memory, bandwidth), potentially leading to slow responses or complete unavailability.
 
* For a large number of HTTP requests, the server may become unresponsive or crash. Net Strike can generate high volumes of HTTP requests, emulating the behavior of multiple clients and stressing the target server.

> [!NOTE]
> Including headers in the HTTP flood requests makes the requests appear more legitimate, as if they are coming from a real browser. This helps to avoid simple filtering mechanisms that may block requests without common headers. You can add more headers if you want.

## ⚙️Troubleshooting

1) `Issue: This script must be run with root privileges?:`  
- Run the tool with sudo.  

2) `Issue: Invalid IP address or hostname?:`  
- Ensure the target domain/IP is correct and reachable.  

3) `Issue: ModuleNotFoundError?:`  
- See Requirements.txt .  

4) `Issue: Python3 or pip not found?:`  
- read the requirements.txt file, (cat requirements.txt) or (gedit requirements.txt).  

5) `Issue:  HTTP requests failing with SSL errors?:`  
- The tool disables SSL verification; check network connection and site availability.  

## 🛠️MODIFICATION 

IF U WANT TO MODIFY OR USE THE SCRIPT IN UR PROJECTs , CONSIDER GIVING CREDITS !  

## 📂Example OutPut

	________________________________________________________________________________
	1)Selecting Attack Type
		[>] Select Attack Type »
  		 1. TCP SYN Flood
   		 2. ICMP Flood
  		 3. UDP Flood
  		 4. HTTP Flood
  		 5. Exit
	Choose the desired attack type and follow the prompts to configure it.
	________________________________________________________________________________
	2)TCP/UDP/ICMP Flood (Example)
		[>] Enter the target IP or hostname » 192.168.1.100
		[>] Enter the packet size » 1024
		[>] Enter how many threads to use » 10
		[>] Enter how long (in seconds) to run the attack » 60
	The tool will start sending packets and log details about each transmission.
	______________________________________________________________________________________________
	3)HTTP Flood (Example)
		[>] Enter the target URL » https://example.com
		[>] Enter how many requests do you want to send in each cycle » 500
		[>] Enter how long (in seconds) to run the attack » 60
	It will start sending multiple HTTP GET requests asynchronously.
	______________________________________________________________________________________________

	*)TCP SYN Flood Output
		[THREAD 1] » 1024 bytes sent to 192.168.1.100 through port 443 from 192.168.50.23
		[THREAD 2] » 1024 bytes sent to 192.168.1.100 through port 80 from 192.168.45.67
		...
		Attack completed. Total data sent: 500MB over 60 seconds.
	______________________________________________________________________________________________
	*)HTTP Flood Output
		HTTP GET request sent to https://example.com  » [ 200 OK ]
		HTTP GET request sent to https://example.com  » [ 503 Service Unavailable ]
		...
		Attack completed. Total requests sent: 10,000 within 60 seconds.

	_______________________________________________________________________________________________


# ⚠️Disclaimer !
This tool is intended for ethical and educational use only.  
Do not use it for illegal activities. The author is not responsible for any misuse.  
This script is intended for educational purposes and authorized testing only.  
Unauthorized use of this script is illegal and unethical.  
Ensure you have explicit permission before testing any system.  
- Obtain explicit permission before testing any system.  
- Adhere to all applicable laws and regulations.  
- Respect user privacy and data.  
- By using this script, you agree to take full responsibility for your actions.  
