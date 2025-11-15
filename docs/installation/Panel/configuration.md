# ⚙️ Configuration

You can edit **OV Panel** by configuring the `.env` file to match your environment. This file controls admin credentials, panel settings, SSL options, and developer options.

During installation the installer will prompt for the main values (admin username/password, port path) and populate the `.env` automatically. Editing the file manually is optional — use these steps if you want to change values after installation:

1. Open the `.env` file in a text editor (example):

```bash
sudo nano /opt/ov-panel/.env
```

2. Make your changes and save the file.

3. Restart the panel service :

```bash
bash <(curl -s https://raw.githubusercontent.com/primeZdev/ov-panel/main/install.sh)
```

The `.env` file is located in to (`/opt/ov-panel/.env`).

---

### 🧾 Example `.env` file
```env
# Admin Credentials
ADMIN_USERNAME=admin
ADMIN_PASSWORD=admin

# UVICORN Settings
HOST=0.0.0.0
URLPATH=dashboard
VITE_URLPATH=dashboard
PORT=9000

### Ssl Configuration
# SSL_KEYFILE="/path/to/keyfile"
# SSL_CERTFILE="/path/to/certfile"

### Development Settings
# DEBUG=INFO
# DOC=True

### Security Settings
JWT_SECRET_KEY="random string here" # change this to a secure random string
JWT_ACCESS_TOKEN_EXPIRES=86400 # in seconds
```

---

### 🔧 Configuration Details

#### 🧍‍♂️ Admin Credentials
| Variable | Description |
|----------|-------------|
| `ADMIN_USERNAME` | The username for logging into the OV Panel. |
| `ADMIN_PASSWORD` | The password for the admin account. |



#### ⚙️ Panel Settings
| Variable | Description |
|----------|-------------|
| `URLPATH` and  `VITE_URLPATH`| The path used in your panel URL (default: `dashboard`). |
| `PORT` | The port number the OV Panel runs on (default: `9000`). |

Example access URL:

`http://your-server-ip:9000/dashboard`

---

#### 🔐 SSL Settings (Optional)
| Variable | Description |
|----------|-------------|
| `SSL_KEYFILE` | Path to your SSL private key file. |
| `SSL_CERTFILE` | Path to your SSL certificate file. |

> To enable HTTPS, uncomment both lines in your `.env` and provide valid certificate paths.

Example:

```env
SSL_KEYFILE=/etc/letsencrypt/live/yourdomain.com/privkey.pem
SSL_CERTFILE=/etc/letsencrypt/live/yourdomain.com/fullchain.pem
```

#### 🛠 Developer Options (Optional)
| Variable | Description |
|----------|-------------|
| `DEBUG` | Logging level. One of: `DEBUG`, `INFO` (default), `WARNING`, `ERROR`, `CRITICAL`. Example: `DEBUG=INFO`. Set to `DEBUG` for verbose output useful when troubleshooting. |
| `DOC` | API documentation |
