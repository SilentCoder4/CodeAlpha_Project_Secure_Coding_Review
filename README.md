# CodeAlpha_Project_Secure_Coding_Review

The **CodeAlpha_Project_Basic_Network_Sniffer** is a Python-based project designed for cybersecurity training. It operates as a low-level network sniffer using raw sockets to capture and analyze network traffic. Below is a security review of its implementation based on the code reviewed from GitHub repositories and common best practices.

## Issues Identified
```
1. Root Privileges Requried
2. No Input Validation
3. Lack of Exception Handling
4. Data Exposure
5. Hardcoded Protocols
```
## Recommendations
```

1. Restrict Privileges
2. Validate Data
3. Handle Exceptions
4. Sanitize Output
5. Use Libraries
```