---
title: How to Install Docker on Ubuntu or Debian
date: 2024-11-03 12:00:00 +0600
categories: [Docker, Ubuntu, Debian]
tags: [docker, installation, ubuntu, debian, beginners]
author: Afrin
---

Docker is a powerful platform that enables developers to build, deploy, and manage applications in isolated environments known as **containers**. If you're new to Docker, this guide provides a step-by-step approach to installing Docker on Ubuntu and Debian-based systems. Let’s get started!

---

## Prerequisites

Before you begin, ensure that you have the following:

- A system running **Ubuntu 20.04+** or **Debian 10+**.
- **Root** or **sudo** privileges on the system.

The following instructions are designed for beginners and will guide you through the installation process.

---

## Step 1: Update Your System

It is recommended to start by updating your existing packages. Open your terminal and run:

```bash
sudo apt update && sudo apt upgrade -y
```

This command will refresh your package list and upgrade any outdated packages to minimize compatibility issues during the installation.

---

## Step 2: Install Required Packages

Next, install packages that will allow you to add Docker's official repository and interact with HTTPS sources. Execute the following command:

```bash
sudo apt install -y ca-certificates curl
```

These packages are essential for securely fetching Docker from its repository.

---

## Step 3: Add Docker’s Official GPG Key

A **GPG key** is essential for ensuring that the software you download originates from a verified source. To add Docker's GPG key, enter the following command:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

This command retrieves Docker’s GPG key and saves it to your system for future verification.

---

## Step 4: Set Up Docker Repository

With the GPG key successfully added, you can now add Docker’s repository to your list of sources.

### For Ubuntu

Run the following command:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### For Debian

For Debian users, execute the following command instead:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

This step configures your system to retrieve Docker packages from the newly added repository.

---

## Step 5: Update the Package Index

To ensure your package manager is aware of the Docker repository, you need to update your package index again:

```bash
sudo apt update
```

---

## Step 6: Install Docker Engine

You are now ready to install Docker. Use the following command:

```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Explanation of the Packages

- **docker-ce**: The Community Edition of Docker.
- **docker-ce-cli**: The command-line interface for interacting with Docker.
- **containerd.io**: A core component responsible for managing container execution.
- **docker-buildx-plugin**: An enhanced build tool for Docker that adds support for multi-platform builds.
- **docker-compose-plugin**: A plugin that enables Docker Compose to manage multi-container applications directly from the Docker CLI.

---

## Step 7: Verify Docker Installation

After installation, check if Docker is running correctly:

```bash
sudo systemctl status docker
```

You should see that the Docker service is **active** and **running**. To confirm that Docker was installed successfully, run:

```bash
docker --version
```

---

## Step 8: Run Docker Without `sudo` (Optional)

By default, Docker commands require **sudo** privileges. To allow your user to run Docker commands without using `sudo`, follow these steps:

1. Add your user to the **docker** group:

   ```bash
   sudo usermod -aG docker $USER
   ```

2. Log out and log back in for the changes to take effect.

3. Test your setup by running:

   ```bash
   docker run hello-world
   ```

   If Docker is set up correctly, this command will download a test image and print a welcome message.

---

## Step 9: Alternative Method: Install Docker Using Proxmox Community Script

For Proxmox VE users, there’s a Docker installation script provided by the Proxmox community that simplifies setting up Docker in an LXC container. This script not only installs Docker but also allows options for **Portainer** and **Docker Compose V2** setup.

### Steps to Use the Proxmox Docker Installation Script

If you’re using Proxmox, open the **Proxmox VE Shell** through the WebUI and follow these steps:

1. **Download the Script**:

   Run the following command to download the Docker setup script from the Proxmox community:

   ```bash
   curl -fsSL https://community-scripts.github.io/Proxmox/scripts/docker-install.sh -o docker-install.sh
   ```

2. **Run the Script**:

   Make the script executable, then run it to install Docker:

   ```bash
   chmod +x docker-install.sh
   sudo ./docker-install.sh
   ```

> **Note**: If the LXC is created as **Privileged**, this script will automatically configure USB passthrough.

1. **Alternative Install for Alpine Linux**:

   To set up a Proxmox VE Docker LXC using Alpine Linux, execute the following in the **Proxmox VE Shell**:

   ```bash
   bash -c "$(wget -qLO - https://github.com/community-scripts/ProxmoxVE/raw/main/ct/docker.sh)"
   ```

   This command sets up Docker in a new Alpine Linux LXC environment on Proxmox VE.

### Usage Tips

- **Run Docker Compose V2**: Use `docker compose` (with a space instead of a hyphen), as Compose V2 has shifted from the `docker-compose` to `docker compose` format.
- **Add Portainer**: The script also provides an option to install **Portainer** for a web-based Docker management interface.

For more detailed documentation or updates to this script, visit the [Proxmox Community Scripts page](https://community-scripts.github.io/Proxmox/scripts?id=Docker).

## Troubleshooting Tips

- **Error with GPG key**: If you encounter an error, ensure that you followed the steps to add the GPG key correctly.
- **Permission issues**: Make sure you use `sudo` where needed or confirm that your user has been added to the `docker` group successfully.

---

## Conclusion

Congratulations! You’ve successfully installed Docker on your Ubuntu or Debian system. Docker is now ready for use, enabling you to experiment with containers and run applications in isolated environments. For further learning, check out more tutorials on our [YouTube channel](https://www.youtube.com/@lewsion) for an in-depth exploration of Docker and other exciting technologies.

Happy Dockering!
[EOF]
