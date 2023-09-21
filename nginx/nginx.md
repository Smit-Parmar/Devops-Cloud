# Nginx

## Introduction

Nginx is a high-performance, open-source web server and reverse proxy server. It is renowned for its efficiency, scalability, and versatility. Nginx is widely used to serve web content, balance traffic, and act as a reverse proxy, making it a crucial component of many web applications and websites.

## Key Features

### 1. Web Server

- Nginx serves as a robust and efficient web server for delivering static and dynamic content to clients.

### 2. Reverse Proxy

- Nginx acts as a reverse proxy server, forwarding client requests to backend application servers. This enables load balancing and improves application scalability.

### 3. Load Balancer

- Nginx functions as a load balancer, distributing incoming traffic across multiple backend servers, ensuring even workload distribution and high availability.

### 4. SSL/TLS Termination

- Nginx handles SSL/TLS encryption and decryption, making it suitable for securing websites with HTTPS. It offloads SSL processing from backend servers, enhancing performance.

### 5. HTTP/2 and HTTP/3 Support

- Nginx supports modern HTTP protocols like HTTP/2 and HTTP/3, providing faster and more efficient data transfer compared to HTTP/1.1.

### 6. Caching

- Nginx offers various caching mechanisms, such as content caching, proxy caching, and FastCGI caching, to reduce server load and improve response times.

## Setup and Configuration

### Installation

- You can install Nginx on your server using package managers like `apt-get` (for Debian/Ubuntu) or `yum` (for CentOS/Red Hat).

  ```bash
  # Debian/Ubuntu
  sudo apt-get update
  sudo apt-get install nginx

  # CentOS/Red Hat
  sudo yum install nginx

### Configuration
Nginx configuration files are typically located in the `/etc/nginx` directory.
The primary configuration file is `nginx.conf`.
Server block configurations (similar to virtual hosts in Apache) are often stored in `/etc/nginx/sites-available/` and symlinked to `/etc/nginx/sites-enabled/`.

### Basic Server Block
```bash
server {
    listen 80;
    server_name example.com;
    root /var/www/html;
    index index.html;
    location / {
        # Additional configuration
    }
}
```