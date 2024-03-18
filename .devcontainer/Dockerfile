# syntax=docker/dockerfile:1

# Comments are provided throughout this file to help you get started.
# If you need more help, visit the Dockerfile reference guide at
# https://docs.docker.com/engine/reference/builder/

FROM node:lts-bookworm as development

# Set the working directory in the container
WORKDIR /usr/app

# Update the system and install necessary packages
RUN apt-get update && \
    apt-get upgrade -y && \
    # This command updates the package lists for the APT (Advanced Package Tool) package manager. 
    # It fetches the latest information about available packages from the configured repositories.
    apt-get clean && \
    # After installing packages, the apt-get clean command is used to clean up the APT package cache. 
    # This removes downloaded package files (.deb) that are no longer needed, reducing the size of the Docker image.
    rm -rf /var/lib/apt/lists/*
    # This command removes the package lists in /var/lib/apt/lists/. 
    # These lists are no longer needed after the package installation is complete, 
    # and removing them helps reduce the size of the Docker image. 
    # The use of rm -rf removes the files and directories forcefully.

# Install latest version of npm
RUN npm install -g npm@latest && \
    corepack enable && \
    yarn set version berry

# Check node version when the container launches
CMD ["node, -v"]
