# Base image: Ubuntu 22.04
FROM ubuntu:22.04

# Maintainer
MAINTAINER Kaltoum K. <metlaouimak@gmail.com>

# Prevent interactive prompts during build
ENV DEBIAN_FRONTEND=noninteractive

# enter  directory
WORKDIR /app

# Install Apache and MySQL
RUN apt-get update && \
    apt-get install -y apache2 mysql-server && \
    apt-get clean

# Add Apache config
ADD apache-config.conf /etc/apache2/sites-available/000-default.conf

# Copy website files
COPY website/ /var/www/html/

# Volume for MySQL data
VOLUME ["/var/lib/mysql"]

# Create and switch to non-root user
RUN useradd -m appuser
USER appuser

# Expose ports
EXPOSE 80 3306

# Start Apache in foreground
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
