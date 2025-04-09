# 🐳 Docker Compose | WordPress with MySQL - 04 APR 2025

Welcome to my **Docker Compose** setup for deploying a **WordPress** site backed by a **MySQL** database! This is based on my learning from **4th April 2025**, showcasing how to structure, manage, and deploy multi-container applications using Docker Compose.

---

## 📘 What is Docker Compose?
> Docker Compose is a tool used to define and manage multi-container Docker applications. It simplifies the process of orchestrating containers by allowing services, networks, and volumes to be declared in a single file.

### 🔑 Benefits:
- ✅ Structured & Readable Configuration
- ✅ Easy Multi-Container Management
- ✅ Built-in Networking between Services
- ✅ Persistent Volumes for Data Management
- ✅ Declarative Syntax & Scalable Architecture

---

## ⚙️ Docker Compose Installation
```bash
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose version
```

---

## 🚀 Quick Start
```bash
# Pull WordPress (Standalone)
docker pull wordpress
docker run -itd -p 8091:80 wordpress
```

---

## 📂 Docker Compose Project Structure
```
docker-wordpress-compose/
├── docker-compose.yml
└── README.md
```

---

## 🧾 docker-compose.yml
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

## ▶️ How to Run
```bash
# Start the application
docker-compose up -d

# Stop and remove containers, networks, and volumes
docker-compose down --volumes
```

Access your WordPress site at 👉 [http://localhost:8000](http://localhost:8000)

---

## 🧠 Key Concepts Covered
- ✅ Docker Compose Services & Volumes
- ✅ Environment Variable Configuration
- ✅ Networking Between Containers
- ✅ WordPress + MySQL Stack

---

## 📩 Connect with Me
- 💻 GitHub: [@laditrinath321](https://github.com/laditrinath321)
- 🔗 LinkedIn: [Trinath Ladi](https://www.linkedin.com/in/trinath-l-2a5720113)
- 📧 Email: [ladi.trinath@gmail.com](mailto:ladi.trinath@gmail.com)

---

> "Structure your containers, scale your apps, and deploy like a pro with Docker Compose!" 🚀

