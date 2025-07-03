# 🚀 NGINX + SSL Reverse Proxy with Certbot – Full Setup Guide

This guide explains how to set up a secure reverse proxy using NGINX and Let's Encrypt SSL certificates via Certbot.

## 🔧 Prerequisites
- A Linux server (Ubuntu/Debian)
- Root or sudo access
- A domain name pointing to your server IP

## 📥 Installation Steps
1. Update your system
```bash
sudo apt update && apt upgrade
```
2. Install NGINX
```bash
sudo apt install nginx
```
3. Install Certbot and Configuration domain in NGINX plugin
```bash
sudo apt install certbot python3-certbot-nginx
```
4. DNS Configuration
 
  Before proceeding, ensure that your DNS records point to your Nginx server’s IP address. Certbot requires DNS records to be correctly configured for the domain you intend to secure.

5. Obtain SSL certificates with Certbot
```bash
sudo certbot --nginx -d emqx.projectenginesecurity.my.id
```
6. Setup auto-renewal
```bash
sudo certbot renew --dry-run
```
## ✅ Test
Run:
```bash
sudo nginx -t
sudo systemctl restart nginx
```
## Access the HTTPS Service

you can access your HTTPS service by navigating to your domain (e.g., https://emqx.projectenginesecurity.my.id). Nginx will route the secure requests to your backend server using the SSL certificate obtained from Certbot.
