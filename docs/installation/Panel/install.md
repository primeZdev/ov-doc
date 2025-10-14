# 🚀 Panel Installation Guide

OV-Panel can be easily installed on your server using the official automated script.  
This guide will walk you through everything you need to get started.

---

## 🧩 Requirements

Before installation, make sure your server meets the following requirements:

| Requirement | Description |
|--------------|-------------|
| 💻 **Operating System** | Ubuntu 20.04+ (Debian-based) |
| 🧠 **Minimum RAM** | 2 GB |
| 🌐 **Domain or Subdomain** | Must be pointed to your server’s IP |
| ⚙️ **Privileges** | Root access or a user with `sudo` permissions |

---

## 🛠️ Installation

To install OV-Panel, simply run the following command in your server terminal:

```bash
bash <(curl -s https://raw.githubusercontent.com/primeZdev/ov-panel/main/install.sh)
```



### 🌐 Using a Domain (Optional but Recommended)

If you want to access your panel using a **domain or subdomain** instead of an IP address:

1. Make sure your **domain is pointed** to your server’s IP address (using an **A record**).  
2. Install an **SSL certificate** for your domain (for example, using **Certbot** or **Nginx Proxy Manager**).  
3. Open your `.env` file located at `/opt/ov-panel` and update ssl path.
4. Save the file and restart the panel to apply the changes:  

> 💡 **Tip:** Using HTTPS improves security and prevents login or session issues.
