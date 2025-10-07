# 2. Jellyfin Media Server Installation and Setup

Jellyfin was installed as the media management and streaming platform.

### 2.1. Jellyfin Installation

1.  **Add Jellyfin Repository:** Followed the official Jellyfin guide to add their APT repository to the Ubuntu server.
2.  **Install Jellyfin:**
    ```bash
    sudo apt install jellyfin
    ```

### 2.2. Library Configuration

1.  **Access Web UI:** Accessed the Jellyfin setup wizard via the local IP (e.g., `http://192.168.1.144:8096`).
2.  **Library Structure:** Created a new TV Shows library and linked it to the primary media share configured in Samba.
3.  **Crucial Naming Convention:** Ensured the media files followed the standard naming convention for reliable metadata matching:
    * **Series Folder:** `TV Shows/The Witcher (2019)/`
    * **Season Folder:** `Season 01/`
    * **Episode File:** `The Witcher - S01E01 - The End's Beginning.mkv`
    
### 2.3. Metadata Plugin

* **TheTVDB:** Installed and enabled the **TheTVDB** plugin for accurate TV series metadata, images, and descriptions.
