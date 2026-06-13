# Better Than Wolves CE — Pterodactyl Egg

A Pterodactyl Panel egg for **Better Than Wolves Community Edition** (BTWCE 3.x) on **Minecraft 1.6.4** with the **Legacy Fabric** loader.

## What it does

On first install, the egg automatically:

1. Downloads the **Legacy Fabric installer** (0.11.1) and runs it in server mode
2. Downloads Minecraft 1.6.4 server files
3. Downloads the **BTWCE mod** from Modrinth (default: 3.1.0)
4. Creates `eula.txt` and default `server.properties`

The loader is pinned to **Legacy Fabric 0.15.11** — the wiki requires this because 0.16+ breaks BTWCE mod compat.

## Requirements

- **Java 17** (handled by `ghcr.io/pterodactyl/yolks:java_17`)
- Pterodactyl Panel v1.x with Wings
- Outbound HTTPS to `maven.legacyfabric.net`, `api.modrinth.com`, `cdn.modrinth.com`

## Import instructions

1. **Admin > Eggs** in your Pterodactyl panel
2. Click **Import Egg**
3. Upload `egg-better-than-wolves-ce.json`
4. Assign the egg to a nest
5. Create a new server using this egg

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `JAVA_XMS` | `512` | Minimum JVM heap (MB) |
| `JAVA_XMX` | `1024` | Maximum JVM heap (MB) |
| `MC_VERSION` | `1.6.4` | Minecraft version (BTWCE 3.x requires 1.6.4) |
| `BTWCE_VERSION` | `3.1.0` | BTWCE mod version (or `latest` for newest release) |
| `MOTD` | `A Better Than Wolves CE Server` | Server MOTD |
| `ONLINE_MODE` | `true` | Mojang auth (set `false` for offline) |

## Server startup command

```
java -Xms${JAVA_XMS}M -Xmx${JAVA_XMX}M -jar fabric-server-launch.jar
```

## Connecting

Once the server is running, connect via **Minecraft 1.6.4** with the Legacy Fabric client and the same BTWCE mod jar in your `mods/` folder.

For friends outside your network, use [playit.gg](https://playit.gg/) for easy tunneling without port forwarding.

## Links

- Wiki (3.0 Beta): https://wiki.btwce.com/view/3.0.0_Beta
- Modrinth mod page: https://modrinth.com/mod/btwce
- Legacy Fabric: https://legacyfabric.net/
- BTW Community GitHub: https://github.com/BTW-Community
- Discord: https://discord.gg/wztckS29th
