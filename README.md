# Better Than Wolves CE — Pterodactyl Egg

A Pterodactyl Panel egg for **Better Than Wolves Community Edition** (BTWCE), based on Minecraft 1.5.2 with the Cursed Fabric loader.

## What it does

On first install, the egg automatically:

1. Downloads and runs the **Cursed Fabric Installer** (server mode)
2. Downloads Minecraft 1.5.2 server files
3. Downloads the latest **Cursed-BTW** mod jar into `mods/`
4. Optionally downloads the **CraftGuide** addon (recommended)
5. Creates `eula.txt` and default `server.properties`

## Requirements

- Java 8 (handled by the Docker image `ghcr.io/pterodactyl/yolks:java_8`)
- Pterodactyl Panel v1.x with Wings

## Import instructions

1. Go to **Admin > Eggs** in your Pterodactyl panel
2. Click **Import Egg**
3. Upload `egg-better-than-wolves-ce.json`
4. Assign the egg to a nest
5. Create a new server using this egg

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `JAVA_XMS` | `512` | Minimum JVM heap (MB) |
| `JAVA_XMX` | `1024` | Maximum JVM heap (MB) |
| `MOTD` | `A Better Than Wolves CE Server` | Server MOTD |
| `ONLINE_MODE` | `true` | Mojang auth (set `false` for offline) |
| `INSTALL_CRAFT_GUIDE` | `1` | Auto-install CraftGuide addon (press G in-game) |

## Server startup command

```
java -Xms${JAVA_XMS}M -Xmx${JAVA_XMX}M -jar fabric-server-launch.jar
```

## Connecting

Once the server is running, connect via Minecraft **1.5.2** using the Fabric client (Prism Launcher recommended — see wiki).

For friends outside your network, use [playit.gg](https://playit.gg/) for easy tunneling without port forwarding.

## Links

- Wiki: https://wiki.btwce.com/view/Installation
- GitHub: https://github.com/BTW-Community
- Discord: https://discord.gg/wztckS29th
- Installer: https://github.com/BTW-Community/legacy-fabric-installer/releases
- BTW Mod: https://github.com/BTW-Community/Cursed-BTW/releases
- CraftGuide: https://github.com/BTW-Community/CraftGuide/releases
