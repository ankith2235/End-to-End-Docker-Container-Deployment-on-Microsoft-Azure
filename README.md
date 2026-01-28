End-to-End Docker Container Deployment on Microsoft Azure
📌 Project Overview

This project demonstrates an end-to-end containerized application deployment on Microsoft Azure using Docker, Azure Virtual Machines, Azure Container Registry (ACR), and Azure App Service.
The goal is to build, store, and deploy a Dockerized application in a scalable and cloud-native way.

🛠️ Technologies Used

Microsoft Azure

Azure Virtual Machine (Linux)

Azure Container Registry (ACR)

Azure App Service (Linux – Container-based)

Docker

Docker Hub

Linux (Ubuntu Server)

🏗️ Project Architecture
Docker Hub Image
      |
      v
Azure Virtual Machine
(Docker Installed)
      |
      v
Custom Docker Image
      |
      v
Azure Container Registry (ACR)
      |
      v
Azure App Service
(Container Deployment)

✅ Tasks Performed
🔹 1. Docker Setup on Azure VM

Created an Azure Linux Virtual Machine

Installed and configured Docker

Pulled a public Docker image from Docker Hub

Modified the container by adding a new file

Committed the changes to create a custom Docker image

🔹 2. Azure Container Registry (ACR)

Created an Azure Container Registry

Connected Docker running on Azure VM to ACR

Tagged the custom Docker image

Pushed the image to ACR

🔹 3. Application Deployment using Azure App Service

Created an Azure App Service (Linux, container-based)

Configured App Service to pull image from ACR

Deployed the containerized application

Verified successful deployment using the App Service default domain

📦 Docker Commands Used
# Install Docker
sudo apt update
sudo apt install docker.io -y

# Pull image from Docker Hub
docker pull hshar/webapp

# Run container
docker run -it hshar/webapp /bin/bash

# Commit changes
docker commit <container_id> hshar/webapp:azure-project

# Login to Azure Container Registry
docker login <acr-name>.azurecr.io

# Tag image for ACR
docker tag hshar/webapp:azure-project <acr-name>.azurecr.io/webapp:v1

# Push image to ACR
docker push <acr-name>.azurecr.io/webapp:v1

🌐 Application Access

After deployment, the application is accessible via the Azure App Service default domain:

https://<app-name>.<region>.azurewebsites.net

🎯 Key Learnings

Docker images are immutable and modified through containers

Azure Container Registry securely stores private images

Azure App Service simplifies container-based deployments

Proper port configuration is essential for containerized apps

End-to-end container deployment improves scalability and portability

🧠 Challenges Faced

Docker permission issues on Linux VM

Azure App Service container startup errors

Port mismatch between container and App Service

Initial browser security warning for new Azure domains

All issues were resolved through correct configuration and logging.

📄 Conclusion

This project successfully demonstrates a real-world DevOps workflow for deploying containerized applications on Microsoft Azure using Docker, ACR, and App Service. It highlights best practices in container management and cloud deployment.
