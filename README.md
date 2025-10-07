# Ubuntu-Home-Media-Server-CGNAT-Bypass
Self-Hosted Media &amp; File Server on Old Laptop | Ubuntu LTS, Jellyfin, Tailscale (CGNAT Bypass)
Project Title: Old Laptop Revival: Secure Home Media Server & File Share with Tailscale

This project documents the complete process of converting an obsolete laptop into a reliable, low-power home server running Ubuntu Server LTS. The server acts as a centralized File Server (Samba/NFS) for local devices and a fully featured Media Server using Jellyfin.

The primary challenge overcome was establishing secure, reliable remote access despite being behind Carrier-Grade NAT (CGNAT), which blocks traditional port forwarding.

🔑 Key Solutions & Takeaways:

    CGNAT Bypass: We successfully replaced a failing PiVPN/WireGuard setup (which was blocked by CGNAT) with Tailscale to create a zero-configuration private network (Tailnet).

    Networking Fundamentals: Comprehensive troubleshooting of persistent "Data Received" failures and empty iptables FORWARD chains, demonstrating a deep understanding of NAT, Masquerading, and IP Forwarding.

    Infrastructure: Setting up and managing persistent services on Linux, including DHCP Reservation via the router and preparing a robust file-sharing environment.

This guide provides a valuable reference for anyone struggling with CGNAT, seeking to repurpose old hardware, or wanting to build their first self-hosted media platform.
