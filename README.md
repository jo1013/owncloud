# ownCloud Installation Guide

This guide provides instructions for installing ownCloud using Docker and as a local installation on Debian 9.0.

## Docker Installation

### 1. Create a new project directory
```bash
mkdir owncloud-docker-server
cd owncloud-docker-server
```

### 2. Download the docker-compose.yml file
```bash
wget https://raw.githubusercontent.com/owncloud/docs/master/modules/admin_manual/examples/installation/docker/docker-compose.yml
```

### 3. Create the environment configuration file
Create a file named `.env` with the following content:
```
OWNCLOUD_VERSION=10.7
OWNCLOUD_DOMAIN=localhost:8080
ADMIN_USERNAME=admin
ADMIN_PASSWORD=admin
HTTP_PORT=8080
```

### 4. Build and start the container
```bash
docker-compose up -d
```

## Local Installation on Debian 9.0

### 1. Add the ownCloud repository
```bash
wget -nv https://download.owncloud.org/download/repositories/production/Debian_9.0/Release.key -O - | sudo apt-key add -
echo 'deb http://download.owncloud.org/download/repositories/production/Debian_9.0/ /' | sudo tee -a /etc/apt/sources.list.d/owncloud.list
```

### 2. Update package list and install ownCloud
```bash
sudo apt update
sudo apt install owncloud-complete-files
```

## Additional Information

For more details and the latest versions, please visit the official ownCloud repository:
[https://download.owncloud.org/download/repositories/production/owncloud/](https://download.owncloud.org/download/repositories/production/owncloud/)
