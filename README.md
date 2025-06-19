In this lab we will capture data in Wireshark using Kali Linux.

In this step, the Kali Linux virtual machine is started and a browser is opened to navigate to http://example.com. This site is used as a safe, non-encrypted test domain for observing HTTP traffic. 
Although most modern browsers auto-upgrade to HTTPS, accessing it manually helps prepare for HTTP analysis.

![example com in Kali](https://github.com/user-attachments/assets/c6694084-c1a2-4850-b674-fe3bd026ff7a)

Wireshark is launched, and the correct active network interface (such as eth0 or enp0s3) is selected to begin capturing packets. A display filter is set to http to isolate and view only HTTP traffic. This filter simplifies analysis by excluding irrelevant protocols.

![select network interface and set filter](https://github.com/user-attachments/assets/f4d3c47a-4a72-4084-86e8-d13b1b1082dd)

Since browsers typically redirect HTTP requests to HTTPS, a curl command is used in the terminal to manually generate an HTTP request. The command curl -v http://example.com ensures the request stays unencrypted, making it visible in Wireshark for inspection.

![Send http request](https://github.com/user-attachments/assets/024bc793-8d52-4cac-b4bb-213e04281ab7)

Packet capture begins in Wireshark on the chosen network interface. When the curl command is run, the HTTP request and response packets appear in real time. These packets can be examined for method, headers, and server response, all in plain text.

![Capturing](https://github.com/user-attachments/assets/23cdae86-54b7-4de8-bf9a-6e61761cbb07)

The nslookup tool is used to resolve the domain example.com into its corresponding IP address. This step confirms that the IP observed in Wireshark matches the actual IP tied to the domain, validating that the traffic being captured is legitimate and related to the target.

![nslookup to verify IP](https://github.com/user-attachments/assets/e2d6d488-1257-44e0-bc42-e88bd9d9a4e9)
