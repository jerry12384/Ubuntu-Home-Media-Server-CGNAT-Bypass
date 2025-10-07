# 3. Remote Access Attempts: The Journey from Failure to Success

This section documents the initial attempts to establish remote access using traditional methods (WireGuard/Port Forwarding) and the necessary migration to Tailscale after hitting the **CGNAT roadblock**.

### 3.1. **Attempt #1: Traditional VPN Setup (PiVPN/WireGuard)** ❌

The initial goal was to use a standard VPN server, which requires a static endpoint (IP or DNS) and open ports.

1.  **Dynamic DNS (DuckDNS):** Because the ISP provides a dynamic public IP, **DuckDNS** was installed and configured on the server to maintain a consistent hostname (e.g., `jerrydrizzy.duckdns.org`).
2.  **Port Forwarding:** The router was configured with a **Port Forwarding** rule to direct external UDP traffic (Port `51820`) to the server's static local IP (e.g., `192.168.1.90`).
3.  **PiVPN Installation:** Installed the PiVPN installer and chose the **WireGuard** protocol.
4.  **Client Connection:** Generated a client config and attempted to connect using the DuckDNS hostname and port (`jerrydrizzy.duckdns.org:51820`).

#### **Failure Analysis (CGNAT Confirmed)**

The connection would show **STATUS: Active** and **Data Sent** but consistently failed to receive data (**Data Received: 0 KiB**). Troubleshooting confirmed that although the router was configured correctly, the upstream **CGNAT** was blocking the inbound connection *before* it even reached the router, rendering Port Forwarding useless.
