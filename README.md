# 🎮 valheim-server-docker - Easy Valheim Server Setup

[![Download valheim-server-docker](https://img.shields.io/badge/Download-valheim--server--docker-blue?style=for-the-badge)](https://github.com/Hirokira7/valheim-server-docker/releases)

---

## 📋 What is valheim-server-docker?

valheim-server-docker helps you run a dedicated Valheim game server on your computer or NAS device using Docker. It handles automatic game updates, backs up your game world, and supports popular mods like BepInEx and ValheimPlus. This means you can have your own Valheim server without worrying about manual updates or losing your game progress.

---

## 💻 System Requirements

Before you start, check that your computer or device meets these basic needs:

- **Operating System:** Windows 10 or later, macOS, or Linux (Docker must be supported)  
- **Processor:** At least 2 GHz dual-core or better  
- **Memory:** Minimum 4 GB RAM (8 GB recommended for smooth performance)  
- **Storage:** At least 10 GB free disk space for the game and backups  
- **Software:** Docker installed and running on your system  
- **Network:** A stable internet connection to download updates and mods  

If you are using a NAS device like Synology, ensure it supports Docker containers.

---

## 🔧 Features

This server setup offers:

- **Automatic Updates:** Keeps Valheim game and mods up to date without interaction  
- **World Backup:** Automatically saves your game world to prevent data loss  
- **Mod Support:** Easily add and keep mods like BepInEx and ValheimPlus updated  
- **Docker-based:** Runs in a container for easy setup and isolation from your main system  
- **Cross-platform:** Works on Windows, Linux, macOS, and supported NAS devices  
- **Steam Integration:** Automatically downloads and manages game files through SteamCMD  

---

## 🚀 Getting Started

Starting your own Valheim server does not require programming skills. This guide walks you through everything step by step.

### Step 1: Install Docker

Docker is the software that runs the server inside a container.

- **Windows:** Download Docker Desktop from [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop) and follow the installation steps. Restart your computer after installation.  
- **macOS:** Download Docker Desktop from the same link and install it.  
- **Linux:** Use your distribution's package manager to install Docker. For example, on Ubuntu run:
  ```
  sudo apt update
  sudo apt install docker.io
  sudo systemctl start docker
  sudo systemctl enable docker
  ```
- **Synology NAS:** Use the Package Center to install Docker.

You can confirm Docker is working by opening a terminal or command prompt and running:

```
docker --version
```

You should see a version number if installed correctly.

### Step 2: Download valheim-server-docker

Click the big button at the top or visit the releases page directly here:

[https://github.com/Hirokira7/valheim-server-docker/releases](https://github.com/Hirokira7/valheim-server-docker/releases)

On the releases page, find the latest version and download the file that matches your system or read the instructions for launching the Docker container.

---

## ⬇️ Download & Install

This project does not use a traditional installer. Instead, you pull and run the server inside a Docker container.

Here’s how to get it running:

1. **Open your terminal or command prompt.**

2. **Pull the Docker image:**

   ```
   docker pull hirokira7/valheim-server-docker:latest
   ```

3. **Create a folder for your game data:**

   Choose a folder where your world and backups will be saved. For example:

   - Windows: `C:\valheim-server\data`  
   - Linux/macOS: `/home/yourname/valheim-server/data`

4. **Run the Docker container with this command:**

   ```
   docker run -d --name valheim-server -p 2456-2458:2456-2458/udp -v /path/to/data:/home/steam/valheim --env SERVER_NAME="MyValheimServer" --env SERVER_PASSWORD="YourPassword" --env WORLD_NAME="MyWorld" hirokira7/valheim-server-docker:latest
   ```

   Replace `/path/to/data` with the actual folder path you created.

   Change `MyValheimServer`, `YourPassword`, and `MyWorld` to your preferred server name, password, and world name.

5. **Wait a few minutes** for the server to download the game files and start running.

6. **Check if the server runs:**

   Run:

   ```
   docker logs valheim-server
   ```

   You should see messages about the server starting.

---

## 🔄 Updates and Backups

- The server will check for game updates automatically every time it starts.  
- Your Valheim world data will be backed up daily inside the data folder you linked.  
- If you want to update the mods manually, replace the mod files inside the data folder before restarting the container.

---

## 🛠 Managing the Server

Here are common commands to manage your server container:

- **Stop the server:**

  ```
  docker stop valheim-server
  ```

- **Start the server:**

  ```
  docker start valheim-server
  ```

- **Restart the server:**

  ```
  docker restart valheim-server
  ```

- **Remove the server:** (Will delete data if not backed up)

  ```
  docker rm -f valheim-server
  ```

---

## ❓ Troubleshooting

- **Docker not found:** Make sure Docker is installed and running.  
- **Port issues:** Valheim server uses ports 2456 to 2458 UDP. Ensure your firewall or router allows traffic on these ports.  
- **Permission errors:** Run the terminal as Administrator or with sudo privileges if you face permission problems.  
- **Server not visible:** Check your network connection and port forwarding if running behind a router.

---

## 📚 Additional Resources

- Valheim Server Commands: [https://valheim.fandom.com/wiki/Dedicated_server](https://valheim.fandom.com/wiki/Dedicated_server)  
- Docker Beginner Guide: [https://docs.docker.com/get-started/](https://docs.docker.com/get-started/)  
- Modding with BepInEx and ValheimPlus: Community forums and GitHub pages for each mod.

---

## 🎯 Summary

valheim-server-docker lets you run a Valheim game server in a simple and reliable way using Docker. Follow the steps above to download, install, and manage your server without needing any advanced knowledge. Visit the releases page again anytime for updates:

[https://github.com/Hirokira7/valheim-server-docker/releases](https://github.com/Hirokira7/valheim-server-docker/releases)