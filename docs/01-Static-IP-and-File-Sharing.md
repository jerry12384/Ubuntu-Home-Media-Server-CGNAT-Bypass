# 1. Server Preparation: Ubuntu, Static IP, and Samba Setup

This section outlines the initial preparation of the old laptop, establishing a stable local network connection, and configuring local file sharing.

### 1.1. Base OS Installation

1.  **Install Ubuntu Server LTS:** Performed a clean installation of the latest Ubuntu Server LTS edition on the old laptop.(If you dont know how to, [here](https://ubuntu.com/tutorials/install-ubuntu-server#1-overview) is a very useful guide).
2.  **Enable SSH:** Ensured SSH is enabled and functional for remote management (`ssh [server_name]@192.168.x.x`).

### 1.2. Network Stability (Critical for Home Server)

For a reliable home server, the local IP address must never change.

1.  **Locate Server MAC Address:** Found the MAC address of the server's primary network interface (`eno1`).
2.  **DHCP Reservation:** Logged into the main router's admin panel and created a **DHCP Reservation** rule. This binds the server's MAC address to a fixed local IP (e.g., `192.168.1.90`).
3.  **Result:** The server now consistently uses the same local IP, preventing access issues within the LAN. *(Note: This is superior to configuring a static IP directly on the Ubuntu OS for simplicity).*

### 1.3. Local File Server Configuration (Samba)

Samba was used to allow Windows, macOS, and Linux devices to easily access and transfer media files to the server over the local network.

1.  **Install Samba:**
    ```bash
    sudo apt install samba
    ```
2.  **Configure Share:** Edited the Samba configuration file (`/etc/samba/smb.conf`) to create the media share:
    ```bash
    [Media]
    path = /mnt/data/media
    browsable = yes
    writable = yes
    guest ok = no
    create mask = 0644
    directory mask = 0755
    valid users = jerryserv1
    ```
3.  **Create Samba User & Restart:**
    ```bash
    sudo smbpasswd -a jerryserv1
    sudo systemctl restart smbd
    ```
