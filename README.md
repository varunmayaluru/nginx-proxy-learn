# Reverse Proxy Setup with Docker Compose

This guide will walk you through setting up a reverse proxy for a simple "Hello, World!" web application using Docker Compose. The setup includes a Python-based HTTP server and an NGINX server acting as a reverse proxy with SSL termination.

### Prerequisites

- Docker installed on your system
- Docker Compose installed
- A valid SSL certificate and key file stored in the `certs/` directory.


#### docker-compose yaml file config precautions (discussing only special)

- In volumes of nginx services, the relative path of certificate files needs to be validated.
- In volumes of nginx services, the relative path of nginx conf needs to be validated.
- Check depends_on if configured and it's correct, as this depends on other service.(nginx)


#### nginx conf file precautions (discussing only special)

- server_name - Point this to correct name
- ssl_certificate, ssl_certificate_key - Point this to correct path in container
- In `location /` and key `proxy_pass` the url must have the service name from docker-compose

### Uderstanding

- There should be link between docker-compose yaml file and nginx conf file

