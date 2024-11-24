# CodeAlpha_Project_Secure_Coding_Review

The [CodeAlpha_Project_Basic_Network_Sniffer](https://github.com/SilentCoder4/CodeAlpha_Project_Basic_Network_Sniffer) is a Python-based project designed for cybersecurity training. It operates as a low-level network sniffer using raw sockets to capture and analyze network traffic. Below is a security review of its implementation based on the code reviewed from GitHub repositories and common best practices.

## Issues Identified
```
1. Root Privileges Requried
   - Running as root for raw socket operations increases the risk of exploitation.
2. No Input Validation
   - The code assumes packet data is valid, risk crashes from malformed packet
3. Lack of Exception Handling
    - Errors like insufficient permission or invalid data are not handled, leading to program crashes.
4. Data Exposure
    - Raw packet data is displayed in the console, Which may unintentionally leak sensitive information.
5. Hardcoded Protocols
    - Usig numerical values for Protocols instead of constants makes the code harder to maintain.
```
## Recommendations
```

1. Restrict Privileges
    - Use CAP_NET_RAW capabilities on linux instead of running as root.
2. Validate Data
    - Check the format and length of incoming packets.
3. Handle Exceptions
    - Add robust error handling for socket creation, permission, and parsing issues.
4. Sanitize Output
    - Limit displayed data to relevant information to avoid exposing sensitive details.
5. Use Libraries
    - High-level libraries like Scapy can improve code mantainability and security.
```