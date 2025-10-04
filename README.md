# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.
## Architecture Diagram:
```mermaid
flowchart TD
    A[User System] --> B[Web Browser]
    A --> C[Email Client]
    B --> D[Network Traffic]
    C --> D
    D --> E[Wireshark Capture Engine]
    E --> F[Protocol Decoders HTTP SMTP IMAP POP]
    F --> G[Browser Artifacts URLs Cookies Auth]
    F --> H[Email Headers Source IP Server Timestamps]
    G --> I[Findings and Reports]
    H --> I
```
## DESIGN STEPS:
### Step 1:
- Install Wireshark and ensure correct network adapter selection.
- Enable packet capturing for your active interface (Wi-Fi/Ethernet).

### Step 2:
**Web Browser Artifact Analysis**
- Open a browser and visit websites with login forms (use dummy credentials).
- In Wireshark, filter traffic with:
    - ```http``` for normal HTTP requests
    - ```http.cookie``` for cookies
    - ```http.authbasic``` for basic authentication
- Identify:
    - URLs visited
    - GET/POST requests
    - Cookies & session IDs
    - Credentials (if plaintext HTTP is used)
### Step 3:
- Capture email traffic by sending/receiving emails (dummy mail server or provided PCAP).
- Use filters:
    - ```smtp``` (Simple Mail Transfer Protocol)
    - ```pop``` / ```imap``` (for received mail)
- Inspect email headers:
    - Source IP
    - Mail server hostname
    - Timestamps
    - Possible forged headers
## PROGRAM:
```mermaid
flowchart TD
    A[Start Wireshark Capture] --> B[Generate Traffic: Web Browsing & Emails]
    B --> C[Apply Protocol Filters: HTTP/SMTP/IMAP/POP]
    C --> D[Extract Browser Artifacts: URLs, Cookies, Credentials]
    C --> E[Analyze Email Headers: Source, Server, Metadata]
    D --> F[Save Findings]
    E --> F[Save Findings]
    F --> G[Generate Digital Forensic Report]
```

## OUTPUT:
Captured Web Activity and Email Header Information

<img width="1919" height="1078" alt="Screenshot 2025-10-04 140356" src="https://github.com/user-attachments/assets/44e30037-30c8-4c8d-a694-43588a22ef98" />

<img width="1910" height="1018" alt="Screenshot 2025-10-04 140503" src="https://github.com/user-attachments/assets/561fb243-9159-409e-85ad-a699aea56217" />

<img width="956" height="1024" alt="Screenshot 2025-10-04 140657" src="https://github.com/user-attachments/assets/ac8c6512-dae3-49da-a500-0f2c0de07c0f" />

<img width="950" height="1019" alt="Screenshot 2025-10-04 140731" src="https://github.com/user-attachments/assets/c9042ab6-3c38-4608-a900-adb2435e2d5f" />

<img width="1919" height="1077" alt="Screenshot 2025-10-04 141342" src="https://github.com/user-attachments/assets/cc28b868-b0f8-4e04-8e4e-da7f3695651b" />


## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark.

