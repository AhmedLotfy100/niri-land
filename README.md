<!-- Screenshots -->
<!-- Screenshots must be uploaded to your GitHub repository to display here. -->
![Overview](./demo-screenshot-overview.png)
![Powermenu](./demo-screenshot-powermenu.png)

# dots

## Dependencies

| Name                        | Used For                                                      | Notes/Link                                                                 |
|-----------------------------|--------------------------------------------------------------|---------------------------------------------------------------------------|
| niri                        | Window manager                                               | [niri](https://github.com/YaLTeR/niri)                                    |
| mako                        | Notifications, volume flyout                                 | [mako](https://github.com/emersion/mako)                                  |
| ImageMagick                 | Background selector                                          | [ImageMagick](https://imagemagick.org/)                                   |
| waybar                      | Overview bar                                                 | [waybar](https://github.com/Alexays/Waybar)                               |
| rofi                        | Powermenu, background selector, app drawer                   | [rofi](https://github.com/davatorium/rofi)                                |
| Babita Classic              | Cursor theme                                                 | [babita-classic](https://github.com/ful1e5/babita-classic)                |
| JetBrains Mono Nerd Font    | Font for UI                                                  | [JetBrainsMono-NF](https://github.com/ryanoasis/nerd-fonts)               |
| GTK Prefer Dark             | Dark theme for GTK apps                                      | Set via `gsettings set org.gnome.desktop.interface color-scheme 'prefer-dark'` |
| Material Design Icons       | Background selector icons                                    | [material-design-icons](https://github.com/Templarian/MaterialDesign)     |
| Papirus Icons               | App drawer icons                                             | [Papirus](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme)   |

## Instructions

- **Install dependencies**: Source all dependencies from your distribution's package manager (e.g., `apt`, `dnf`, `pacman`, etc.).
- **Configs**: Place configuration files in `~/.config`.
- **Scripts**: Place custom scripts in `~/.local/bin`.
- **Autostart**: Start `mako`, `waybar`, `swww-daemon`, and `overviewlistener` via systemd user services (recommended, see [niri docs](https://github.com/YaLTeR/niri#autostart)) or in your niri config.
    - Example systemd user service:  
      ```
      [Unit]
      Description=Start mako
      [Service]
      ExecStart=/usr/bin/mako
      [Install]
      WantedBy=default.target
      ```
    - Enable with:  
      `systemctl --user enable --now mako.service`
    - Alternatively, add to niri config:
      ```
      exec mako
      exec waybar
      exec swww-daemon
      exec overviewlistener
      ```
- **GTK Dark Theme**:  
  Run:  
  `gsettings set org.gnome.desktop.interface color-scheme 'prefer-dark'`