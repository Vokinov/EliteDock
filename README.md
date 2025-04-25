Elitedock - Docker Compose Setup
================================

Elitedock is a simple and secure Docker Compose stack built for running Nextcloud securely with automatic SSL through Traefik, PostgreSQL as a database, and Redis as a caching backend.

Services included:
- Nextcloud (cloud storage)
- Traefik (reverse proxy with automatic SSL via Let's Encrypt)
- PostgreSQL (database backend)
- Redis (cache)

Prerequisites:
--------------
- Docker and Docker Compose installed.
- Publicly accessible IP or domain (DuckDNS recommended).

DuckDNS Setup:
--------------
Elitedock uses DuckDNS to manage dynamic DNS and allow automatic SSL certificate generation.

1. Create an account on DuckDNS:
   https://www.duckdns.org/

2. After logging in, create your own subdomain, e.g.:
   your-subdomain.duckdns.org

3. Copy your unique DuckDNS token from your DuckDNS account page.

4. Update your ".env" file (use ".env.example" as a template):
   DUCKDNS_TOKEN=your-duckdns-token
   DUCKDNS_DOMAIN=your-subdomain.duckdns.org

Getting Started:
----------------
1. Clone this repository to your server:
   git clone https://github.com/yourusername/Elitedock.git
   cd Elitedock

2. Create your ".env" file:
   cp .env.example .env
   Edit the ".env" file to include your DuckDNS token, domain, database credentials, and Nextcloud admin credentials.

3. Launch the Docker Compose stack:
   docker compose -f elitedock.yml up -d

4. Remember to create proper settings for your router firewall

Your Nextcloud instance will now be available securely via HTTPS at:
https://your-subdomain.duckdns.org

License:
--------
MIT License (see LICENSE file).
