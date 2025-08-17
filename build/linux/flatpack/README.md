# Little Navmap Flatpak

A Flatpak package for Little Navmap, a flight planning and navigation tool for flight simulators.

## Building the Flatpak

### Prerequisites

- `flatpak-builder`
- KDE runtime and SDK:
  ```bash
  flatpak install flathub org.kde.Platform//5.15-23.08
  flatpak install flathub org.kde.Sdk//5.15-23.08
  ```

### One-liner to generate .flatpak file

```bash
flatpak-builder --repo=repo builddir org.flatpak.littlenavmap.yml --force-clean && flatpak build-bundle repo org.flatpak.littlenavmap.flatpak org.flatpak.littlenavmap
```

## Project Structure

- [`org.flatpak.littlenavmap.yml`](org.flatpak.littlenavmap.yml) - Main Flatpak manifest
- [`org.flatpak.littlenavmap.desktop`](org.flatpak.littlenavmap.desktop) - Desktop entry file
- `LittleNavmapPortable/` - Source application files
- `builddir/` - Build output directory
- `repo/` - Local Flatpak repository

## Application Details

- **Runtime:** org.kde.Platform/x86_64/5.15-23.08
- **Command:** littlenavmap.sh (wrapper script)
- **Permissions:** Network, filesystem access, X11/Wayland graphics

The application includes proper library path configuration and desktop integration.