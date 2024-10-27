# Emby Docker Compose Setup

This repository provides a fully containerized setup for Emby, an open-source media server. It enables you to easily set up and manage Emby on your home server with Docker Compose.

## 📜 Overview

Emby organizes your media content and makes it accessible on various devices. This project aims to simplify the setup and deployment of an Emby server with Docker Compose, providing a customizable, lightweight solution.

## ⚙️ Features

- **Containerized Setup**: Run Emby as a Docker container for easy deployment.
- **Volume Mapping**: Persist data and configurations across restarts.
- **Network Configuration**: Exposes necessary ports to allow access across your local network.
- **Customizable Environment Variables**: Configure your Emby setup through environment variables.

## 🛠️ Requirements

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## 🚀 Getting Started

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/hexatomek/emby-dockerized.git
    cd emby-dockerized
    ```

2. **Update the `vars.env` file**: See the `vars.env` file and update it with your configuration.

3. **Run Docker Compose**:
    ```bash
    docker-compose up -d
    ```

## 📂 Folder Structure

```plaintext
├── docker-compose.yml   # Docker Compose configuration
├── vars.env             # Example environment variables
└── README.md            # Project documentation


Please use the official Docker Hub documentation: https://hub.docker.com/r/emby/embyserver

🔧 Configuration

    Volumes:
        /config: Stores Emby configuration files.
        /media: Location of your media files.

    Environment Variables:
        Adjust TZ (timezone) and other optional parameters in .env.

📝 Example docker-compose.yml

yaml

version: '3.8'

services:
  emby:
    image: emby/embyserver:latest
    container_name: emby
    ports:
      - "8096:8096"
    environment:
      - TZ=${TZ}
    volumes:
      - ${CONFIG_PATH}:/config
      - ${MEDIA_PATH}:/media
    restart: unless-stopped

🐳 Usage

Access Emby on your server at http://localhost:8096 or http://<your-server-ip>:8096.
🔄 Updating

To update the Emby image, simply pull the latest version and restart the container:

bash

docker-compose pull
docker-compose down
docker-compose up -d

🤝 Contributions

Feel free to open issues or submit pull requests if you'd like to improve this project!
📄 License

This project is licensed under the MIT License.

vbnet


This template should give a comprehensive overview for anyone looking to understand and deploy your Emby setup! Let me know if you'd like further customization on any section.