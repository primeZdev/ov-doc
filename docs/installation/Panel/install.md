# 🚀 Panel Installation Guide

OV-Panel can be easily installed on your server using the official automated script. This guide will walk you through everything you need to get started.

---

## 📋 Prerequisites
### System Requirements

| Requirement | Description |
|-------------|-------------|
| 💻 **Operating System** | Ubuntu 20.04+ / Debian 11+ (Recommended) |
| 🖥️ **CPU** | 1 core minimum (2+ cores recommended) |
| 🧠 **RAM** | 2 GB minimum (4 GB recommended) |
| 💾 **Storage** | 10 GB free space |
| 🌐 **Network** | Stable internet connection |
| 🔑 **Access** | Root access or user with `sudo` privileges |
| 🌍 **Domain** | Domain or subdomain pointed to server IP (optional but recommended) |

- tip "Pro Tip"
    Using a domain with SSL certificate is highly recommended for security and better user experience.

---

## 🛠️ Installation Steps

### Step 1: Run the Installation Script

Connect to your server via SSH and run the following command:

```bash
bash <(curl -s https://raw.githubusercontent.com/primeZdev/ov-panel/main/install.sh)
```

- info What happens during installation?
    - Install required dependencies
    - Download and configure OV-Panel
    - Set up the database
    - Create initial configuration files
    - Start the panel service

- Once installation is complete, you can access your panel:
    -     ```
    http://YOUR_SERVER_IP:port/path
    ```
---

## 🌐 SSL Certificate Setup (Recommended)
### Option 1: Using Certbot (Free SSL)

```bash
# Install Certbot
sudo apt update
sudo apt install certbot

# Generate certificate
sudo certbot certonly --standalone -d your-domain.com
```

### Option 2: Using Cloudflare

1. Point your domain to Cloudflare DNS
2. Enable "Full (strict)" SSL mode in Cloudflare
3. Use Cloudflare Origin Certificate

### Update Panel Configuration

After obtaining your SSL certificate, update the `.env` file:

```bash
nano /opt/ov-panel/.env
```

Add or update these lines:

```bash
SSL_KEYFILE=/path/to/your/certificate.crt
SSL_CERTFILE=/path/to/your/private.key
```

Restart the panel:

```bash
bash <(curl -s https://raw.githubusercontent.com/primeZdev/ov-panel/main/install.sh)
```

---


## 🔧 Post-Installation

After successful installation, proceed to:

- **[Install Nodes](../Node/install.md)** - Add servers to your network
- **[Configure Panel](configuration.md)** - Customize settings and preferences

---

