# Book Lounge WordPress - Docker Setup

This project demonstrates running **WordPress locally** using **Docker**, **MySQL**, and **Nginx** with **HTTPS**, plus a customized homepage banner.

---

## 🚀 Setup Instructions

1. **Open PowerShell** and navigate to the project folder:

```powershell
Set-Location -Path 'Your Project Path'
```

2. **Create SSL certificates** (if not already done):

```powershell
mkdir certs
cd certs
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout localhost.key -out localhost.crt -subj "/C=US/ST=State/L=City/O=BookLounge/OU=Dev/CN=localhost"
cd ..
```

3. **Start Docker containers**:

```powershell
docker-compose up -d
```

This will start:

- WordPress (`wordpress_app`)
- MySQL (`wordpress_db`)
- Nginx (`wordpress_nginx`) with HTTPS

4. **Access WordPress**:

- Open [https://localhost](https://localhost)
- Accept the browser warning for self-signed certificate
- Complete WordPress setup form (site title, username, password)
- Login: [https://localhost/wp-admin](https://localhost/wp-admin)

---

## 🗽 Common Issues & Solutions

1. Database connection error - Ensure db container is running (docker ps)
2. SSL warning - Normal for self-signed certificates; accept warning in browser
3. Port 443 in use - Stop other services using port 443
4. File path issues on Windows - Make sure project folders match paths in docker-compose.yml

---
