---
updated: 2025-09-30T15:05
created: 2025-09-30T09:33
---
secure [[http]], internet traffic can be intercepted so we must encrypt it using [[certificates]]

### diagram
```mermaid
%%{init: {'theme':'base', 'themeVariables': {'background':'transparent','primaryColor':'#21262d','primaryTextColor':'#e6edf3','primaryBorderColor':'#3d444d','lineColor':'#8b949e','secondaryColor':'#161b22','tertiaryColor':'#161b22','mainBkg':'#21262d','nodeBorder':'#3d444d','clusterBkg':'transparent','titleColor':'#e6edf3','edgeLabelBackground':'#161b22','actorBkg':'#21262d','actorBorder':'#3d444d','actorTextColor':'#e6edf3','actorLineColor':'#8b949e','signalColor':'#8b949e','signalTextColor':'#e6edf3','noteBkgColor':'#161b22','noteTextColor':'#e6edf3','noteBorderColor':'#3d444d','labelBoxBkgColor':'#161b22','labelTextColor':'#e6edf3','loopTextColor':'#8b949e'}}}%%
sequenceDiagram

participant Browser

participant Server

participant CA as Certificate Authority

  

Browser->>Server: Connect over HTTPS (port 443)

Server-->>Browser: Sends certificate (public key + identity info)

Browser->>CA: Verify certificate signature (using CA's root cert)

CA-->>Browser: Confirms authenticity (server identity is valid)

Browser->>Server: Generate session key (encrypted with server's public key)

Server-->>Browser: Decrypts session key (with private key)

Browser-->>Server: Encrypted communication established

Server-->>Browser: Encrypted communication established
```