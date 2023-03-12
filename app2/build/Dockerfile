# Use the official PHP image as the base image
FROM php:latest

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any necessary dependencies
RUN apt-get update && \
    apt-get install -y libpq-dev && \
    docker-php-ext-install pdo pdo_pgsql

# Expose port 80 to the outside world
EXPOSE 8081

# Start the PHP server to serve the application
CMD ["php", "-S", "0.0.0.0:8081"]
