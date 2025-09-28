# Use a lightweight Debian base (has apt)
FROM debian:bullseye-slim

# Install dependencies: fortune-mod & cowsay
RUN apt-get update && \
    apt-get install -y fortune-mod cowsay netcat-openbsd && \
    rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Copy the wisecow files to container
COPY . .

# Make sure the script is executable
RUN chmod +x wisecow.sh

# Expose the application port (default in script is 4499)
EXPOSE 4499

# Run the script when container starts
CMD ["./wisecow.sh"]
