# Simple Python Port Scanner
 
I have created a lightweight, dependency-free port scanner Python script. It checks a small set of commonly used TCP ports on localhost and reports whether each one is open or closed, along with the name of the service typically associated with that port.
<h2>Languages Used</h2>

- <b>Python</b> 


<h2>Environments Used </h2>

- <b>PyCharm</b>

---

## Features
 
- Zero third-party dependencies — uses only the built-in `socket` module
- Scans well-known ports for common services (FTP, SSH, Telnet, HTTP, HTTPS, SMB, RDP)
- Fast timeout (0.5s per port) so the scan completes quickly
- Proper socket cleanup after every connection attempt
- Simple, readable output showing port number, status, and service name
## How It Works
 
The script maintains a dictionary mapping port numbers to their commonly associated service names:
 
```python
PORT_NAMES = {
    21: "FTP",
    22: "SSH",
    23: "Telnet",
    80: "HTTP",
    443: "HTTPS",
    445: "SMB",
    3389: "RDP"
}
```
 
For each port, it:
1. Creates a new TCP socket (`AF_INET`, `SOCK_STREAM`)
2. Sets a 0.5 second timeout so unresponsive ports don't hang the scan
3. Attempts a connection to `127.0.0.1` using `connect_ex()`, which returns an error indicator instead of raising an exception
4. Prints whether the port is open (`status == 0`) or closed, along with the associated service name
5. Closes the socket in a `finally` block, guaranteeing cleanup even if something goes wrong mid-connection



<p align="center">
<img width="780" height="554" alt="Screenshot 2026-07-15 at 5 09 46 PM" src="https://github.com/user-attachments/assets/3e434302-37bb-4ab5-86ba-2407f078e958" />
<img width="764" height="167" alt="Screenshot 2026-07-15 at 5 17 26 PM" src="https://github.com/user-attachments/assets/6d331d80-3ee5-4b47-b01e-2ec309b5f85a" />



 
<br />
<br />

## Disclaimer
 
This tool is intended for scanning hosts you own or have explicit permission to test. Scanning systems without authorization may be illegal in your jurisdiction. Use responsibly.
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@

