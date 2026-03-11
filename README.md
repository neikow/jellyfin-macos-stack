# Jellyfin MacOS Stack

---

## 💡 Rationale

Jellyfin is a powerful, open-source media server that allows you to organize, manage, and stream your personal media collection. 
This stack is designed to run on macOS, providing a seamless experience for users who want to set up their own media server.

The stack is heavily inspired by the Zenodya's [blog post](https://zerodya.net/self-host-jellyfin-media-streaming-stack/). You can find their setup in [this repo](https://github.com/Zerodya/docker-compose?tab=readme-ov-file).

Using Docker and Docker Compose allows for easy deployment and quick iteration of the server.

ProtonVPN is my VPN of choice for securing the connection and protecting your privacy while browsing and accessing media online, you may want to fork this repository and change the VPN provider to your preferred one in the `docker-compose.yml` file.

## Setup Instructions

### 1. Download Jellyfin on your MacOS machine
Using Docker is not supported on Apple Silicon Macs, as per the [Jellyfin wiki]().
You will need to download and install the Jellyfin app directly on you machine.

### 2. Clone this repository
```bash
git clone git@github.com:neikow/jellyfin-macos-stack.git
```

### 3. Populate the `.env` file
```bash
cp .env.example .env
```

`MEDIA_DIR` should point to the location of your media files on your MacOS machine. It can be any local or remote location, as long as it can be accessed by Finder.

### 4. Run the stack
```bash
docker compose up -d
```

### 5. Configure Arrs
*arr services (Radarr, Sonarr, Bazarr) need to be configured to point to your Jellyfin media library and download clients.

#### a. 

### 6. Configure your Proxy

If you are using a reverse proxy like Nginx or Traefik, make sure to configure it to route traffic to the Jellyfin server.
I recommend using [nginx-proxy-manager](https://nginxproxymanager.com/) for an easy-to-use web interface.

Services are exposed on the following ports by default:
- Jellyfin: `8096` (HTTP)
- Jellyseer: `5055`
- Jackett: `9117`
- Firesolverr: `8191`
- Transmission: `9091`
- Radarr: `7878`
- Sonarr: `8989`
- Bazarr: `6767`

## Missing Features
- [**Wizarr**](https://docs.wizarr.dev/): A user invitation system, to watch movies and series with friends.
- [**Lidarr**](https://lidarr.audio/): Music collection manager for Usenet and BitTorrent users.

## ⚠️ Legal Notice and Anti-Piracy Warning
This Jellyfin setup is intended for personal media management of legally owned content only.

### Important Legal Guidelines:
**Only use content you legally own**: This includes DVDs, Blu-rays, digital purchases, and other media you have legally acquired.<br>
**Respect copyright laws**: Downloading, sharing, or streaming copyrighted content without proper authorization is illegal in most jurisdictions.<br>
**Personal use only**: This setup is designed for organizing and accessing your personal media library, not for distributing content to others<br>
**No piracy support**: This project does not endorse, support, or provide guidance for obtaining copyrighted content through illegal means

### Your Responsibility:
By using this Jellyfin stack, you acknowledge that:

You are solely responsible for ensuring all content in your media library is legally obtained
You understand and will comply with all applicable copyright laws in your jurisdiction
Any misuse of this software for illegal activities is entirely your responsibility
The maintainers of this project are not responsible for how you choose to use this software. Use it legally and responsibly.

