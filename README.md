# owncloud


# Create a new project directory
mkdir owncloud-docker-server

cd owncloud-docker-server

# Copy docker-compose.yml from the GitHub repository
wget https://raw.githubusercontent.com/owncloud/docs/master/modules/admin_manual/examples/installation/docker/docker-compose.yml

# Create the environment configuration file
cat << EOF > .env
OWNCLOUD_VERSION=10.7
OWNCLOUD_DOMAIN=localhost:8080
ADMIN_USERNAME=admin
ADMIN_PASSWORD=admin
HTTP_PORT=8080
EOF

# Build and start the container
docker-compose up -d



## local형 설치 key 등록

wget -nv https://download.owncloud.org/download/repositories/production/Debian_9.0/Release.key -O - | sudo apt-key add -

echo 'deb http://download.owncloud.org/download/repositories/production/Debian_9.0/ /' | sudo tee -a /etc/apt/sources.list.d/owncloud.list
sudo apt update
sudo apt install owncloud-complete-files

--
### @@출처@@ https://download.owncloud.org/download/repositories/production/owncloud/
