
---

# dots

<!-- Screenshots -->

![Overview](./demo-screenshot-overview.png)
![Powermenu](./demo-screenshot-powermenu.png)

## Dependencies

| Name        | Purpose                                    | Link                                                      |
| ----------- | ------------------------------------------ | --------------------------------------------------------- |
| niri        | Window manager                             | [niri](https://github.com/YaLTeR/niri)                    |
| mako        | Notifications, volume flyout               | [mako](https://github.com/emersion/mako)                  |
| waybar      | Overview bar                               | [waybar](https://github.com/Alexays/Waybar)               |
| swww        | Wallpaper daemon                           | [swww](https://github.com/Horus645/swww)                  |
| rofi        | Powermenu, background selector, app drawer | [rofi](https://github.com/davatorium/rofi)                |
| ImageMagick | Background selector                        | [ImageMagick](https://github.com/ImageMagick/ImageMagick) |

### UI & Icon Themes

| Name                     | Purpose                  | Link                                                                                                 |
| ------------------------ | ------------------------ | ---------------------------------------------------------------------------------------------------- |
| Bibata Classic           | Cursor theme             | [Bibata Cursor](https://github.com/ful1e5/Bibata_Cursor)                                             |
| JetBrains Mono Nerd Font | UI font                  | [JetBrainsMono-NF](https://github.com/ryanoasis/nerd-fonts)                                          |
| Material Symbols Rounded | Background selector font | [Material Symbols Rounded](https://github.com/google/material-design-icons/tree/master/variablefont) |
| Papirus                  | App drawer icons         | [Papirus](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme)                              |

## Installation & Setup

1. **Install dependencies** for your distribution.
2. **Configs**: Copy `.config` files to `~/.config`.
3. **Scripts**: Copy scripts from `bin` to `~/.local/bin`.
4. **Autostart**: Link services with `niri-service` or a display manager:

   ```
   systemctl --user add-wants niri.service mako.service
   systemctl --user add-wants niri.service waybar.service
   systemctl --user add-wants niri.service swww.service
   systemctl --user add-wants niri.service overviewlistener.service
   ```

   Alternatively, start services with `spawn-at-startup` in your niri config.
   [More info](https://yalter.github.io/niri/Configuration%3A-Miscellaneous.html#spawn-at-startup)

## Optional: GTK Theme, Font & Icon Setup

Enable dark mode and unify GTK apps (and some others like Firefox):

```
gsettings set org.gnome.desktop.interface color-scheme 'prefer-dark'
gsettings set org.gnome.desktop.interface gtk-theme 'Adwaita-dark'
gsettings set org.gnome.desktop.interface font-name 'JetBrains Mono Nerd Font 11'
gsettings set org.gnome.desktop.interface icon-theme 'Papirus'
```

> These settings primarily affect GTK apps, though some other apps may be influenced depending on your environment.

---
