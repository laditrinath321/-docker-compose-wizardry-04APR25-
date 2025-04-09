# 🐳💥 Docker Compose Magic: WordPress + MySQL | `04 APR 2025`

> ⚙️ *Build once, deploy anywhere — your very own WordPress site powered by Docker magic!*



---

## ✨ What's Inside This Project?

This repository is a **real-time implementation** of deploying **WordPress** with **MySQL** using Docker Compose. Based on my learning from **April 4th, 2025**, it includes an elegant and scalable way to handle containerized apps.

---

## 🧠 TL;DR Overview

| 🔧 Feature          | ✅ Enabled |
| ------------------- | --------- |
| Multi-Container App | ✅         |
| Declarative Config  | ✅         |
| Persistent Storage  | ✅         |
| Service Networking  | ✅         |
| Easy Scalability    | ✅         |

---

## 📥 Install Docker Compose

```bash
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) \
  -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose version
```

---

## 🔥 One-Liner Launch (Standalone WordPress)

```bash
docker pull wordpress
docker run -itd -p 8091:80 wordpress
```

---

## 📂 Project Structure

```bash
docker-wordpress-compose/
├── docker-compose.yml
└── README.md
```

---

## 📦 docker-compose.yml (Paste Ready ✨)

```yaml
version: "3.3"

services:
  db:
    image: mysql:5.7
    volumes:
      - db_data:/var/lib/mysql
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: somewordpress
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress

  wordpress:
    depends_on:
      - db
    image: wordpress:latest
    volumes:
      - wordpress_data:/var/www/html
    ports:
      - "8000:80"
    restart: always
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress

volumes:
  db_data: {}
  wordpress_data: {}
```

---

## 🚀 Run Your Containers

```bash
# Launch the stack
🟢 docker-compose up -d

# Tear down everything
🔴 docker-compose down --volumes
```

📍 Access your WordPress site at: [http://localhost:8000](http://localhost:8000)

---

## 🎯 Highlights & Concepts

- 🧱 Service Linking with `depends_on`
- 🗃️ Persistent Data using Docker Volumes
- 🌐 Internal Networking via Compose
- ⚙️ Environment Variables for Config
- 🚀 One-command startup for full app stack

---

## 📸 Preview (Sneak Peek)

> *What you launch is what you get!*



---

## 🤝 Let's Connect!

| 🌐 Platform | 🔗 Link                                                         |
| ----------- | --------------------------------------------------------------- |
| 💻 GitHub   | [@laditrinath321](https://github.com/laditrinath321)            |
| 🔗 LinkedIn | [Trinath Ladi](https://www.linkedin.com/in/trinath-l-2a5720113) |
| ✉️ Email    | [ladi.trinath@gmail.com](mailto\:ladi.trinath@gmail.com)        |

---

> ✨ *"Structure your containers, scale your apps, and deploy like a pro with Docker Compose!"* 💥

---

