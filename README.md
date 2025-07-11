# ❄️ icewm-setup

![Made for Debian](https://img.shields.io/badge/Made%20for-Debian-A81D33?style=for-the-badge&logo=debian&logoColor=white)

A minimal but functional IceWM rice script for Debian-based systems.  
Installs all core packages, window manager configs, and themes — ready to go out of the box.

> Part of the [JustAGuy Linux](https://github.com/drewgrif) window manager collection.

<img width="3440" height="1440" alt="2025-07-11_17-26" src="https://github.com/user-attachments/assets/6aaa3bd2-298e-4a7a-a08d-318988b49a09" />

---

## 🚀 Installation

### Quick Install
```bash
git clone https://github.com/drewgrif/icewm-setup.git
cd icewm-setup
chmod +x install.sh
./install.sh
```

### Installation Options

The installer supports the following options:

```bash
./install.sh [OPTIONS]

Options:
  --only-config      Only copy config files (skip packages and external tools)
  --export-packages  Export package lists for different distros and exit
  --help             Show help message
```

**New Features:**
- **Export packages**: Use `--export-packages` to see equivalent package lists for Arch Linux and Fedora
- **Streamlined installation**: Simpler, more reliable installation process
- **Better error handling**: Installation fails fast on errors to prevent partial setups

**Package Installation:** Packages are installed in logical groups (core, UI, file manager, audio, utilities, terminal, fonts) for better organization.

### Distribution-Agnostic Installation

<details>
<summary><strong>⚠️ UNSUPPORTED: Instructions for other distributions (click to expand)</strong></summary>

**IMPORTANT:** These instructions are provided as-is for advanced users. Non-Debian distributions are **NOT officially supported**. Package names and availability may vary. Use at your own risk.

**Arch Linux:**
```bash
# Install dependencies (package names may differ)
sudo pacman -S icewm rofi dunst picom thunar \
  xorg-xbacklight pamixer pavucontrol feh flameshot firefox \
  network-manager-applet xfce4-power-manager ttf-font-awesome

# Copy configuration files
./install.sh --only-config
```

**Fedora:**
```bash
# Install dependencies (package names may differ)
sudo dnf install icewm rofi dunst picom thunar \
  xbacklight pamixer pavucontrol feh flameshot firefox \
  network-manager-applet xfce4-power-manager fontawesome-fonts

# Copy configuration files
./install.sh --only-config
```

**openSUSE:**
```bash
# Install dependencies (package names may differ)
sudo zypper install icewm rofi dunst picom thunar \
  xbacklight pamixer pavucontrol feh flameshot firefox \
  NetworkManager-applet xfce4-power-manager fontawesome-fonts

# Copy configuration files
./install.sh --only-config
```

</details>

### Advanced Usage Examples

```bash
# Export package lists for other distributions
./install.sh --export-packages

# Update only configuration files (useful for non-Debian systems)
./install.sh --only-config
```

**Note:** The script can be run from any location - it automatically detects its directory.

---

## 📦 What It Installs

| Component             | Purpose                          |
|------------------------|----------------------------------|
| `icewm`               | Traditional window manager       |
| `icewm-themes`        | Additional themes for IceWM      |
| `picom` `(FT-Labs)`   | Compositor for transparency      |
| `rofi`                | Application launcher             |
| `dunst`               | Notifications                    |
| `wezterm`             | Terminal emulator                |
| `firefox-esr`         | Default web browser              |
| `thunar` + plugins    | File manager                     |
| `nala`                | Better apt frontend              |
| `pipewire`            | Audio handling                   |
| `flameshot`,          | Screenshot tools                 |
| `micro`               | Terminal text editor             |
| `redshift`            | Night light                      |
| `qimgv`               | Lightweight image viewer         |
| `fzf`, etc.           | Utilities & enhancements         |

**Optional during install:**
- `geany` + plugins - Lightweight IDE (installer will prompt)

> 📄 _Need help with Geany? See the full guide at [justaguylinux.com/documentation/software/geany](https://justaguylinux.com/documentation/software/geany)_

---

## 🎨 Appearance & Theming

- Minimal theme with custom wallpapers
- Native IceWM taskbar with system tray and workspace switching
- Dunst, rofi, and GTK themes preconfigured
- Wallpapers stored in `~/.config/icewm/wallpaper`
- GTK Theme: [Orchis](https://github.com/vinceliuice/Orchis-theme)
- Icon Theme: [Colloid](https://github.com/vinceliuice/Colloid-icon-theme)

> 💡 _Special thanks to [vinceliuice](https://github.com/vinceliuice) for the excellent GTK and icon themes._

---

## 🔑 Keybindings Overview

| Key Combo              | Action                                |
|------------------------|----------------------------------------|
| `Super + Return`       | Launch terminal (wezterm)              |
| `Super + Shift + Return` | Launch floating terminal             |
| `Super + Space`        | Launch rofi application launcher       |
| `Super + r`            | Launch rofi run dialog                 |
| `Super + Tab`          | Show window switcher                   |
| `Super + b`            | Launch Firefox                         |
| `Super + f`            | Launch file manager (Thunar)           |
| `Super + l`            | Lock screen                            |
| `Print`                | Take screenshot (GUI)                  |
| `Shift + Print`        | Take full screenshot to clipboard      |

Keybindings are configured via IceWM's native configuration system.

---

## 📂 Configuration Files

```
~/.config/icewm/
├── preferences            # Main IceWM preferences
├── keys                   # Keybinding configuration
├── menu                   # Application menu
├── toolbar                # Toolbar configuration
├── theme                  # Theme selection
├── startup                # Startup applications
├── themes/
│   └── (custom themes)
├── scripts/
│   ├── autostart.sh
│   ├── changevolume
│   └── power
└── wallpaper/
    └── (wallpaper images)
~/.config/dunst/
└── dunstrc
~/.config/rofi/
├── config.rasi
├── keybinds.rasi
└── power.rasi
~/.config/picom/
└── picom.conf
```

### Terminal Configuration

The setup uses wezterm as the default terminal emulator, launched via:
- `Super + Return`: Launch terminal
- Application menu or desktop shortcuts

Terminal configuration can be customized through:
- `~/.config/wezterm/wezterm.lua` - Main terminal configuration
- IceWM preferences for default terminal application

---

## 🎨 Modular Configuration

This IceWM setup uses a clean configuration approach for better organization:
- **preferences**: Main IceWM configuration and behavior settings
- **keys**: Custom keybinding definitions
- **menu**: Application menu structure
- **toolbar**: Taskbar and system tray configuration
- **theme**: Visual appearance and themes
- **startup**: Autostart applications and scripts

This organized approach makes it easy to:
- Understand and modify specific aspects of the configuration
- Customize the desktop experience to your preferences
- Maintain a clean and functional desktop environment

---

## 📺 Watch on YouTube

Want to see how it looks and works?  
🎥 Check out [JustAGuy Linux on YouTube](https://www.youtube.com/@JustAGuyLinux)
