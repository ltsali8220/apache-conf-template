# Apache Configuration Template

This repository provides standardized, modular Apache HTTP Server configuration files suitable for managing virtual hosts, SSL certificates, and reusable project structures in modern environments.

📌 Repository: [ltsali8220/apache-conf-template](https://github.com/ltsali8220/apache-conf-template.git)

---

## 📁 Directory Structure

```
.
├── etc/
│   └── apache2/
│       └── sites-available/
│           ├── 0000-constants.conf
│           └── sample-site.conf
├── home/
│   └── user/
│       └── vhosts/
│           └── ssl/
│               ├── decode-x509-certificate.sh
│               └── generate-self-signed-ssl.sh
```

---

## ⚙️ Features

- Apache 2.4+ compatible
- Modular configuration using a shared constants file
- Built-in HTTP to HTTPS redirection
- SSL-ready (Self-signed or Let's Encrypt)
- Secure directory settings and best practices
- PHP-FPM compatible (just uncomment in config)

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/ltsali8220/apache-conf-template.git
cd apache-conf-template
```

### 2. Install Configuration Files

Copy the `.conf` files into your Apache config directory:

```bash
sudo cp etc/apache2/sites-available/*.conf /etc/apache2/sites-available/
```

### 3. Enable the Site and Reload Apache

```bash
sudo a2ensite sample-site.conf
sudo systemctl reload apache2
```

### 4. Generate a Self-Signed SSL Certificate (Optional for Dev)

```bash
cd home/user/vhosts/ssl/
bash generate-self-signed-ssl.sh my.sample.site
```

---

## 🖥️ Windows Git Line Ending Notes

If you're using Git on Windows, you may see:

```
LF will be replaced by CRLF
```

### ✅ Fix: Normalize Line Endings

```bash
git config core.autocrlf true
```

### ✅ Recommended `.gitattributes` (Add to root of repo)

```
*.sh text eol=lf
*.conf text eol=lf
```

This ensures shell scripts and config files retain proper Unix-style line endings across platforms.

---

## 🔐 Security Notes

- SSL enabled with **TLSv1.2+** only (no deprecated protocols)
- Logs are separated per site: `error_log` and `access_log`
- Uses `Require all granted` for Apache 2.4 compatibility
- Let's Encrypt paths are supported (commented in config)
- PHP-FPM and CGI support available via optional includes

---

## 📄 License

MIT License

```
MIT License

Copyright (c) 2025 Salivan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.
```

---

## 👤 Maintainer

**Salivan V.**  
Cyber Forensic Professional 
GitHub: [ltsali8220](https://github.com/ltsali8220)

---

## 🤝 Contribute

Contributions are welcome!  
Feel free to open issues or submit pull requests for improvements, fixes, or new features.

---

✅ Save this content as `README.md` in the root of your project folder.
