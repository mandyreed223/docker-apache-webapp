# Start with Ubuntu 24.04 LTS
FROM ubuntu:24.04

# Install Apache without interactive prompts
RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y apache2 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Copy our webpage into Apache's document root
COPY index.html /var/www/html/index.html

# Document that Apache listens on port 80
EXPOSE 80

# Run Apache in the foreground so the container stays alive
CMD ["apachectl", "-D", "FOREGROUND"]