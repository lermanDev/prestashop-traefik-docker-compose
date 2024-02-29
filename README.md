# Docker Compose for PrestaShop with Traefik

This Docker Compose setup provides a quick and secure way to deploy PrestaShop with an automatic SSL certificate generation via Traefik. It includes a MySQL database and is designed for production environments, ensuring easy scalability and security.

## Features
* Automatic SSL Certificate Generation: Utilizes Traefik as a reverse proxy to automatically generate and renew SSL certificates from Let's Encrypt.
* Quick Startup: Launch your entire stack within seconds, without the need for manual configuration.
* Debugging and Monitoring: Traefik's dashboard on port 8080 for real-time monitoring and debugging.
* Isolated Networks: Separates backend and frontend services into different Docker networks for enhanced security.
* Persistent Data Storage: Utilizes Docker volumes for persistent storage of MySQL and PrestaShop data.

## Prerequisites
* Docker and Docker Compose installed on your host.
* A domain name pointed to your server's IP.

## Getting Started

1. Clone the Docker Compose File: Download the docker-compose.yml to your project directory.

2. Configure Your Environment:
 * Replace tudominio@tudominio.com with your email address in the Traefik service configuration.
 * Update the MYSQL_ROOT_PASSWORD, MYSQL_USER, and MYSQL_PASSWORD with secure passwords.
 * Set PS_DOMAIN to your domain name.

3. Create External Network: If not already created, initialize the web network:
    docker network create web
4. Launch the Stack:
    docker-compose up -d

5. Access the PrestaShop Installation: Navigate to https://yourdomain.com to complete the PrestaShop setup.
6. Traefik Dashboard: Access the Traefik dashboard at http://yourserverip:8080 for insights and management of your routes, services, and certificates.

## Advantages
* Security: Automatic HTTPS with SSL certificates and isolated networks.
* Ease of Use: Simple configuration and deployment with Docker Compose.
* Scalability: Easily scale your PrestaShop instance by adjusting the Docker Compose configuration.
* Maintenance: Easy updates and maintenance through Docker containers.

## Customization
You can customize the Docker Compose file further to suit your specific needs, such as adjusting volume paths or adding more services.

## Backup and Restore
Backup: Regularly backup your mysql_data and prestashop_data volumes to avoid data loss.
Restore: Use Docker volume backup files to restore your PrestaShop and MySQL data if necessary.

## Troubleshooting
Ensure your domain name correctly points to your server's IP address.
Check the Traefik logs for any errors with SSL certificate generation or routing issues:

    docker-compose logs traefik

## Conclusion
This Docker Compose setup provides a robust, secure, and scalable solution for deploying PrestaShop with minimal effort. The automatic SSL certificate generation and easy configuration make it an ideal choice for both development and production environments.

