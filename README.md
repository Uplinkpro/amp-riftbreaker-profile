# The Riftbreaker - AMP Template

AMP (Application Management Panel) template for The Riftbreaker Dedicated Server.

## Features

- **Steam App ID:** 4114030 (Free dedicated server app)
- **Windows & Linux Support:** Runs natively on Windows, uses Proton 8.0 on Linux
- **Docker Recommended on Linux:** Uses `cubecoders/ampbase:wine-stable` container
- **Co-op Support:** Up to 4 players
- **Configurable Settings:** Server name, password, game mode, difficulty, and more

## Installation

### Method 1: Add as Custom Repository (Recommended)

1. Fork this repository to your own GitHub account
2. Update the `manifest.json` file:
   - Change `"url"` to your forked repository URL
   - Optionally change `"prefix"` to your preferred prefix
3. In AMP, navigate to **Configuration → Instance Deployment**
4. Click **Add** under **Configuration Repository**
5. Enter your repository in the format: `YOUR_USERNAME/riftbreaker-amp-template:main`
6. Click **Fetch**
7. Refresh your browser
8. The template will appear when creating a new instance with the prefix you set

### Method 2: Submit to Official CubeCoders Repository

To contribute to the official repository:

1. Fork [CubeCoders/AMPTemplates](https://github.com/CubeCoders/AMPTemplates)
2. Copy these files to the root of your fork:
   - `riftbreaker.kvp`
   - `riftbreakerconfig.json`
   - `riftbreakermetaconfig.json`
   - `riftbreakerports.json`
   - `riftbreakerupdates.json`
3. **Do NOT include** `manifest.json` or `README.md` in your pull request
4. Submit a pull request to the main repository

## Files Included

| File | Description |
|------|-------------|
| `riftbreaker.kvp` | Main configuration file |
| `riftbreakerconfig.json` | Settings manifest (UI configuration) |
| `riftbreakermetaconfig.json` | Config file mappings |
| `riftbreakerports.json` | Network port definitions |
| `riftbreakerupdates.json` | SteamCMD update stages |
| `manifest.json` | Repository manifest for AMP |

## Configuration Options

| Setting | Description | Default |
|---------|-------------|---------|
| Server Name | Name shown in server browser | My Riftbreaker Server |
| Server Password | Password to join (optional) | Empty |
| Max Players | Maximum players (1-4) | 4 |
| Public Server | List in public browser | True |
| Game Mode | Campaign or Survival | Campaign |
| Difficulty | Easy/Normal/Hard/Brutal | Normal |
| Allow Mods | Allow modded clients | False |

## Network Ports

| Port | Protocol | Purpose |
|------|----------|---------|
| 27015 | UDP | Game Traffic |
| 27016 | UDP | Query/Browser |

## Notes

- The dedicated server app (4114030) is free to download and supports anonymous SteamCMD login
- On Linux, the template downloads Proton 8.0 (Steam App ID 2348590) automatically
- Docker is recommended on Linux to avoid manually installing Wine dependencies
- Console regex patterns may need adjustment based on actual server output

## Troubleshooting

### Executable Not Found
If the server fails to start, verify the executable name. The template assumes `riftbreaker_ds.exe`. Check the downloaded files in `4114030/` and update `App.ExecutableWin` in the kvp file if different.

### Linux Issues
Ensure Docker is enabled for the instance, or manually install Wine and its dependencies on the host.

## License

This template is provided as-is for community use with AMP.

## Links

- [The Riftbreaker on Steam](https://store.steampowered.com/app/780310/The_Riftbreaker/)
- [Official Website](https://www.riftbreaker.com/)
- [AMP by CubeCoders](https://cubecoders.com/AMP)
- [AMP Generic Module Wiki](https://github.com/CubeCoders/AMP/wiki/Configuring-the-'Generic'-AMP-module)
