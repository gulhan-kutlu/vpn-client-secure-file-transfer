# vpn-client-secure-file-transfer

### VPN Client Configuration for Secure File Transfers

### Overview
> This project demonstrates the configuration and verification of a secure IPsec VPN client
for protected file transfers across an untrusted network.

> The lab focuses on comparing secure and non-secure file transfer methods
and validating encryption, tunnel integrity, and packet-level security.

### Technologies & Tools
- Windows VPN Client (IKEv2 / IPsec)
- AES-256 Encryption
- PowerShell
- Wireshark
- FTP vs SSH File Transfers

### VPN Route Configuration & Connectivity Verification

The screenshot below shows the successful addition of a VPN route
using PowerShell and verification of connectivity to the remote network
via ICMP ping.

- Route added for 172.30.0.0/24
- Traffic routed through IPsec VPN interface
- Successful ping response from remote host (172.30.0.2)

### VPN Route and Ping Verification
<img width="641" height="461" alt="Screenshot 2025-12-25 at 12 02 43 PM" src="https://github.com/user-attachments/assets/2032d9ce-f6c7-421e-82f1-cad4a2c2cf5f" />

### Key Security Concepts
- IPsec tunnel establishment (IKE_SA_INIT, IKE_AUTH)
- ESP encrypted traffic verification
- Clear-text vs encrypted credential exposure
- VPN tunnel validation using ping and tracert

### Implementation Summary
- Configured an IPsec VPN client using IKEv2
- Verified AES-256 encryption on the tunnel
- Captured and analyzed FTP traffic showing clear-text credentials
- Captured and analyzed SSH traffic showing encrypted payloads
- Validated ESP traffic and VPN routing behavior
- Attempted custom IPsec policy configuration using PowerShell

### Findings
- FTP transfers expose credentials and file contents in clear text
- SSH encrypts authentication and file data end-to-end
- IPsec ESP traffic prevents payload inspection at the packet level
- VPN tunnel failures were identified during CREATE_CHILD_SA negotiation


### Disclaimer
> This project was completed in a controlled lab environment for educational purposes.

### What This Project Demonstrates
- Hands-on configuration of an IPsec VPN client using IKEv2
- Ability to verify encryption and tunnel integrity at packet level
- Clear understanding of why FTP is insecure over untrusted networks
- Practical comparison of insecure vs secure file transfer protocols

