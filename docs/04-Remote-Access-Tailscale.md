# 3. Remote Access Solution: Tailscale (CGNAT Bypass)

Since Port Forwarding failed due to CGNAT [1], Tailscale was implemented as the zero-configuration mesh VPN solution.

### 3.1. Tailscale Installation

Installed the [package](https://tailscale.com/download/linux) using the official commands on the Ubuntu server:

```bash
# Example commands (exact commands depend on Ubuntu version but were executed successfully)
curl -fsSL [https://pkgs.tailscale.com/stable/ubuntu/jammy.noarch.gpg](https://pkgs.tailscale.com/stable/ubuntu/jammy.noarch.gpg) | sudo dd of=/usr/share/keyrings/tailscale-keyring.gpg
# ... (rest of the installation commands)
sudo tailscale up
