# dots

<!-- Screenshots -->
<!-- Screenshots must be uploaded to your GitHub repository to display here. -->
![Overview](./demo-screenshot-overview.png)
![Powermenu](./demo-screenshot-powermenu.png)

## Dependencies

| Name        | Used For                        | Notes/Link                                         |
|-------------|---------------------------------|----------------------------------------------------|
| niri        | Window manager                  | [niri](https://github.com/YaLTeR/niri)             |
| mako        | Notifications, volume flyout    | [mako](https://github.com/emersion/mako)           |
| waybar      | Overview bar                    | [waybar](https://github.com/Alexays/Waybar)        |
| swww        | Wallpaper daemon                | [swww](https://github.com/Horus645/swww)           |
| rofi        | Powermenu, background selector, app drawer | [rofi](https://github.com/davatorium/rofi) |
| ImageMagick | Background selector             | [ImageMagick](https://imagemagick.org/)            |

### UI & Icon Themes

| Name                        | Used For                       | Notes/Link                                                                 |
|-----------------------------|--------------------------------|---------------------------------------------------------------------------|
| Babita Classic              | Cursor theme                   | [babita-classic](https://github.com/ful1e5/babita-classic)                |
| JetBrains Mono Nerd Font    | Font for UI                    | [JetBrainsMono-NF](https://github.com/ryanoasis/nerd-fonts)               |
| Material Symbols            | Background selector font        | [material-symbols](https://github.com/google/material-design-icons/tree/master/font) |
| Papirus               | App drawer icons               | [Papirus](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme)   |

## Instructions

- **Install dependencies**: Source all dependencies for your distribution.
- **Configs**: Place configuration files from `.config` in `~/.config`.
- **Scripts**: Place scripts from `bin` in `~/.local/bin`.
- **Autostart**: Setup autostart using the commands below. Linking services requires starting niri with `niri-service` or via a display manager.  
  For more info, see [Example systemd Setup](https://yalter.github.io/niri/Example-systemd-Setup.html).
  ```
  systemctl --user add-wants niri.service mako.service
  systemctl --user add-wants niri.service waybar.service
  systemctl --user add-wants niri.service swww.service
  systemctl --user add-wants niri.service overviewlistener.service
  ```
  Alternatively, start each service using `spawn-at-startup` in your niri config.

## Optional: GTK Theme, Font & Icon Setup

To enable dark mode and for uniformity across GTK apps (and some others like Firefox), you can set the theme, font, and icon theme with:
```
gsettings set org.gnome.desktop.interface color-scheme 'prefer-dark'
gsettings set org.gnome.desktop.interface gtk-theme 'Adwaita-dark'
gsettings set org.gnome.desktop.interface font-name 'JetBrains Mono Nerd Font 11'
gsettings set org.gnome.desktop.interface icon-theme 'Papirus'
```
Note: These settings only apply to GTK apps, but may affect others (e.g., Firefox) depending on your environment.