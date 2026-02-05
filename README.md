# Millennium Installer (PowerShell)

Updates or installs **Millennium** to a given version (or `latest`) using a small set of optional PowerShell arguments.

The script automatically:

- Fetches the correct GitHub release
- Downloads the appropriate Windows ZIP asset
- Installs or updates Millennium
- Optionally starts Steam when finished

---

## Requirements

- Windows
- PowerShell 5.1+ (or PowerShell 7+)
- An existing Steam installation

---

## Usage

### Install / update to the latest version

```powershell
irm "https://clemdotla.github.io/millennium-installer-ps1/millennium.ps1" | iex
```

---

## Arguments

| Argument     | Description                                                       | Type   | Default  |
| ------------ | ----------------------------------------------------------------- | ------ | -------- |
| `-NoLog`     | Disables all console output                                       | Switch | `false`  |
| `-NoWarn`    | Remove the "longer" warning                                       | Switch | `false`  |
| `-DontStart` | Prevents Steam from starting automatically after installation     | Switch | `false`  |
| `-SteamPath` | Overrides automatic Steam path detection (with fallback)          | String | Auto     |
| `-Version`   | Installs a specific version instead of the latest (with fallback) | String | `latest` |

---

## Examples

### Install a specific version

```powershell
iex "& { $(irm 'https://clemdotla.github.io/millennium-installer-ps1/millennium.ps1') } -Version 'v2.31.1'"
```

### Silent install (no logs, do not start Steam)

```powershell
iex "& { $(irm 'https://clemdotla.github.io/millennium-installer-ps1/millennium.ps1') } -NoLog -DontStart"
```

### Custom Steam path

```powershell
iex "& { $(irm 'https://clemdotla.github.io/millennium-installer-ps1/millennium.ps1') } -SteamPath 'E:\\Steam'"
```

---

## Notes

- If a specified version cannot be found, the script automatically falls back to the latest available release.
- The installer prioritizes Windows ZIP assets from GitHub releases.
- GitHub API rate limits may apply when running the script frequently without authentication.

---

## Credits

- **[clem.la](https://discord.com/users/868170669412745216)** (Discord)
- Original Millennium project by [SteamClientHomebrew](https://github.com/SteamClientHomebrew)
