
---
title: How to Install Docker on Ubuntu or Debian
date: 2024-11-03 12:00:00 +0600
categories: [Docker, Ubuntu, Debian]
tags: [docker, installation, ubuntu, debian, beginners]
author: afrin
---

# How to Install Docker on Ubuntu or Debian

Docker is a powerful tool that allows developers to create, deploy, and run applications in isolated environments called **containers**. If you're new to Docker, this guide will walk you through the process of installing Docker on Ubuntu and Debian-based systems. Let's get started!

---

## Prerequisites

To install Docker, make sure you have:
- A system running **Ubuntu 20.04+** or **Debian 10+**.
- **Root** or **sudo** privileges.

We’ll be covering the steps in a way that's easy for beginners to follow.

---

## Step 1: Update Your System

First, it's a good idea to update your existing packages. Open a terminal and run:

```bash
sudo apt update
sudo apt upgrade
```

This will ensure your system is up-to-date and minimize compatibility issues during installation.

---

## Step 2: Install Required Packages

Next, we need to install a few packages that allow us to add Docker’s official repository and work with HTTPS sources.

Run the following command in your terminal:

```bash
sudo apt install ca-certificates curl
```

These packages will help us securely fetch Docker from its repository.

---

## Step 3: Add Docker’s Official GPG Key

A **GPG key** ensures that the software you download is from a verified source. To add Docker's GPG key, enter:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

This command downloads Docker’s key and saves it to your system for verification.

---

## Step 4: Set Up Docker Repository

With the GPG key added, you can now set up Docker’s repository.

### For Ubuntu:

Run:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### For Debian:

Run:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

This command adds Docker’s repository to your list of sources.

---

## Step 5: Update the Package Index

To ensure your system is aware of the Docker repository, update your package index again:

```bash
sudo apt update
```

---

## Step 6: Install Docker Engine

Now, we’re ready to install Docker! Use this command:

```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

```

### What These Packages Mean:

- **docker-ce**: The Docker Community Edition.
- **docker-ce-cli**: The command-line interface for Docker.
- **containerd.io**: A core component of Docker for managing container execution.
- **docker-buildx-plugin**: An advanced build component for Docker that extends the capabilities of docker build with support for multi-platform builds.
- **docker-compose-plugin**: A plugin that enables Docker Compose to manage multi-container applications directly through the Docker CLI.
---

## Step 7: Verify Docker Installation

Once installed, check if Docker is running correctly with:

```bash
sudo systemctl status docker
```

You should see that the Docker service is **active** and **running**.

Additionally, confirm Docker is installed by running:

```bash
docker --version
```

---

## Step 8: Run Docker Without `sudo` (Optional)

By default, Docker requires **sudo** privileges. To allow your user to run Docker without `sudo` each time, follow these steps:

1. Add your user to the **docker** group:

   ```bash
   sudo usermod -aG docker $USER
   ```

2. Log out and log back in for the changes to take effect.

3. Test the setup by running:

   ```bash
   docker run hello-world
   ```

   If Docker is set up correctly, this command will download a test image and print a welcome message.

---

## Troubleshooting Tips

- **Error with GPG key**: Ensure you followed the steps to add the GPG key correctly.
- **Permission issues**: Confirm you’re using `sudo` where needed or that your user is added to the `docker` group.

---

## Conclusion

You’ve successfully installed Docker on Ubuntu or Debian! Docker is now ready to use, and you can start experimenting with containers to run applications in isolated environments. Check out more tutorials on our [YouTube channel](#) for a deeper dive into Docker and other exciting technologies.

Happy Dockering!