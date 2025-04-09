
# 🐳 Docker Compose - Learning Notes (04 APR 2025)

Docker Compose is a tool for defining and managing multi-container Docker applications. With a single YAML file, you can configure all your application's services, making it easier to set up complex environments.

---

## ✨ Why Use Docker Compose?
- 🔧 Simplifies container management with one command (`up`, `down`)
- 📁 Structure your configuration for clarity and maintainability
- 🔄 Declarative setup of your desired container state
- 📦 Multi-container orchestration made easy

---

## 📌 Key Features:
- **Multi-Container Management**
- **Service Dependencies (`depends_on`)**
- **Built-in Networking** for communication via service names
- **Volume Management** for persistent data
- **Scalability** via `--scale`

---

## 🧰 Installation Steps (Ubuntu)
```bash
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose version
```

---

## 🐘 Sample WordPress + MySQL Setup

📄 `docker-compose.yml`
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

## 🚀 Commands to Run

```bash
# Start the stack
docker-compose up -d

# Stop and remove containers, networks, and volumes
docker-compose down --volumes
```

---

## 🔗 Bonus
```bash
# Pull the WordPress image and run manually
docker pull wordpress
docker run -itd -p 8091:80 wordpress
```

---

📅 **Date:** 04 APR 2025  
👨‍💻 **Author:** Trinath Ladi  
