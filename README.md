# ✨ Niri Land

![Background Selector](./assets/bgselector.png)

## Features
- [x] Status bar only visible in overview
- [x] Gapless windows  
- [x] Waybar color adapts to wallpaper 
- [x] Wallpaper selector  
- [x] App drawer  
- [x] Power menu  
- [x] Volume flyout with mute indicator  
- [ ] Blur

## Screenshots

![App Drawer](./assets/appdrawer.png)
![Overview](./assets/overview.png)
![Power Menu](./assets/powermenu.png)

## Dependencies

| Name          | Used For                                   | Link                                                      |
| ------------- | ------------------------------------------ | --------------------------------------------------------- |
| `niri`        | Window manager                             | [niri](https://github.com/YaLTeR/niri)                    |
| `mako`        | Notifications, volume flyout               | [mako](https://github.com/emersion/mako)                  |
| `waybar`      | Overview bar                               | [waybar](https://github.com/Alexays/Waybar)               |
| `swww`        | Wallpaper daemon                           | [swww](https://github.com/Horus645/swww)                  |
| `rofi`        | Powermenu, background selector, app drawer | [rofi](https://github.com/davatorium/rofi)                |
| `ImageMagick` | Background selector                        | [ImageMagick](https://github.com/ImageMagick/ImageMagick) |

### UI & Icon Themes

| Name                       | Used For                 | Link                                                                                                 |
| -------------------------- | ------------------------ | ---------------------------------------------------------------------------------------------------- |
| `Bibata Classic`           | Cursor theme             | [Bibata Cursor](https://github.com/ful1e5/Bibata_Cursor)                                             |
| `JetBrains Mono Nerd Font` | UI font                  | [JetBrainsMono-NF](https://github.com/ryanoasis/nerd-fonts)                                          |
| `Material Symbols Rounded` | Background selector font | [Material Symbols Rounded](https://github.com/google/material-design-icons/tree/master/variablefont) |
| `Papirus`                  | App drawer icons         | [Papirus](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme)                              |

## Installation & Setup

1. **Install dependencies** for your distribution.
2. **Configs**: Copy `.config` files to `~/.config`.
3. **Scripts**: Copy scripts from `bin` to `~/.local/bin`.
4. **Wallpapers**: Copy images from `wallpapers/` into `~/Pictures/wallpapers`.
5. **Autostart**: Link services with `niri` (preferred). This requires starting niri with `niri-session` or a display manager:

   ```bash
   systemctl --user add-wants niri.service mako.service
   systemctl --user add-wants niri.service waybar.service
   systemctl --user add-wants niri.service swww.service
   systemctl --user add-wants niri.service overviewlistener.service
   ```

   Alternatively, add these lines to `~/.config/niri/config.kdl`:

   ```kdl
   spawn-at-startup "waybar"
   spawn-at-startup "mako"
   spawn-at-startup "swww-daemon"
   spawn-at-startup "overviewlistener"
   ```

## Keybinds

| Action              | Shortcut  |
| ------------------- | --------- |
| Background selector | `Mod + B` |
| App drawer          | `Mod + D` |
| Power menu          | `Mod + P` |

## Optional: GTK Theme, Font & Icon Setup

Enable dark mode and unify GTK apps (and some others like Firefox):

```bash
gsettings set org.gnome.desktop.interface color-scheme 'prefer-dark'
gsettings set org.gnome.desktop.interface gtk-theme 'Adwaita-dark'
gsettings set org.gnome.desktop.interface font-name 'JetBrains Mono Nerd Font 11'
gsettings set org.gnome.desktop.interface icon-theme 'Papirus'
```
