# Better Than Wolves CE — Pterodactyl Egg

A Pterodactyl/Pelican Panel egg for **Better Than Wolves Community Edition** (BTWCE 3.x) on **Minecraft 1.6.4** with the **Legacy Fabric** loader.

## What it does

On first install (run via "Reinstall Server" in the panel), the egg automatically:

1. Downloads the **Legacy Fabric installer 1.1.1** and runs it in server mode
2. Downloads Minecraft 1.6.4 server files
3. Downloads the **BTWCE mod** from Modrinth (default: 3.1.0)
4. Creates `eula.txt` and default `server.properties`

The install script is **idempotent** — re-running it on a working install is a no-op.

## ⚠️ Important notes (different from the wiki)

The wiki is **out of date**. Two things had to change to make this work:

| Wiki says | Egg uses | Why |
|-----------|----------|-----|
| LF installer 0.11.1 | LF installer **1.1.1** | 0.11.1 has a bug where the lwjgl-platform artifact path is wrong (no-classifier version) for MC 1.6.4. It 404s on the legacy fabric maven. |
| Loader 0.15.x | Loader **0.18.0+** | BTWCE 3.1.0's `fabric.mod.json` declares `fabricloader >= 0.18.0`. Older loaders will be rejected at startup with `Incompatible mods found!`. |

These were both confirmed by reading the BTWCE 3.1.0 jar and by reproducing the install locally.

## Requirements

- **Java 17** (handled by `ghcr.io/pterodactyl/yolks:java_17`)
- Pterodactyl/Pelican Panel v1.x with Wings
- Outbound HTTPS to `maven.legacyfabric.net`, `api.modrinth.com`, `cdn.modrinth.com`

## Import instructions

1. **Admin > Eggs** in your Pterodactyl/Pelican panel
2. Click **Import Egg**
3. Upload `egg-better-than-wolves-ce.json`
4. Assign the egg to a nest
5. Create a new server using this egg
6. **Click "Reinstall Server"** to run the install script
7. **Click "Start"** to launch the server

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `JAVA_XMS` | `512` | Minimum JVM heap (MB) |
| `JAVA_XMX` | `1024` | Maximum JVM heap (MB) |
| `MC_VERSION` | `1.6.4` | Minecraft version (BTWCE 3.x requires 1.6.4) |
| `BTWCE_VERSION` | `3.1.0` | BTWCE mod version (or `latest` for newest release) |
| `LOADER_VERSION` | `0.18.0` | Legacy Fabric loader (BTWCE 3.1.0 requires >= 0.18.0) |
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
