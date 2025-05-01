# 🌑 DarkSide Dotfiles

These are my personal dotfiles for a Wayland-based Arch Linux environment using [Hyprland](https://github.com/hyprwm/Hyprland). It includes configuration for my terminal, bar, launcher, notifications, and more.

## 📂 Managed Configs

- `alacritty` – GPU-accelerated terminal emulator
- `gtk-3.0`, `gtk-4.0` – Theming and UI styling for Thunar
- `hypr` – Hyprland window manager config
- `mako` – Notification daemon for Wayland
- `neofetch` – System info CLI
- `rofi` – Launcher (Wayland fork)
- `waybar` – Wayland status bar
- `wofi` – dmenu-style app launcher

---
## 🔧 Installation
📦 Dependencies

Before using these configs, install the following packages:

from pacman
```bash
sudo pacman -S --needed \
  git alacritty hyprland mako neofetch \
  waybar wofi brightnessctl pipewire pipewire-pulse \
  ttf-jetbrains-mono-nerd wireplumber nwg-look \
  imagemagick chafa
```
from AUR
```bash
yay -S rofi-lbonn-wayland-git papirus-folders-git #Use your preferred AUR manager
```
🛠️ Installed Dependencies
| Package                          | Description                                                                  |
|----------------------------------|------------------------------------------------------------------------------|
| **alacritty**                    | A GPU-accelerated terminal emulator.                                         |
| **hyprland**                     | A Wayland-based window manager.                                              |
| **mako**                         | Notification daemon for Wayland.                                             |
| **neofetch**                     | A command-line system information tool.                                      |
| **rofi-lbonn-wayland-git**       | Wayland-compatible fork of the Rofi app launcher.                            |
| **waybar**                       | A customizable Wayland status bar.                                           |
| **wofi**                         | A dmenu-style application launcher for Wayland.                              |
| **brightnessctl**                | Command-line tool for adjusting screen brightness.                           |
| **pipewire**                     | A server and processing framework for multimedia in Linux.                   |
| **pipewire-pulse**               | A PulseAudio replacement for Pipewire.                                       |
| **ttf-jetbrains-mono-nerd**      | JetBrains Mono font with Nerd Fonts patched icons.                           |
| **wireplumber**                  | A session manager for Pipewire.                                              |
| **nwg-look**                     | A tool for customizing the appearance of Wayland desktop environments.       |
| **imagemagick**                  | Software suite for creating, editing, and converting bitmap images.          |
| **chafa**                        | Command-line utility to display images in the terminal.                      |
| **git**                          | a tool for tracking changes and managing code versions                       |
| **papirus-folders-git**          | Papirus folder icons for file managers.                                      |

Clone the repository:
```bash
git clone --bare https://github.com/Skilledcamman/DarkSide-dotfiles.git $HOME/.dotfiles
```

Define an alias:
```bash
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
```

Backup dotfiles(if necessary):
```bash
mkdir -p ~/.dotfiles-backup
dotfiles checkout 2>&1 | grep -Eo '\.config/[^ ]+' | while read file; do
  mkdir -p "$(dirname "$HOME/.dotfiles-backup/$file")"
  mv "$HOME/$file" "$HOME/.dotfiles-backup/$file"
done
```

Checkout the dotfiles:
```bash
dotfiles checkout
```

Hide untracked files:
```bash
dotfiles config --local status.showUntrackedFiles no
```

Add folder Icons:
```bash
papirus-folders -C white #check [papirus-folders](https://github.com/PapirusDevelopmentTeam/papirus-folders} for more options
```
use nwg-look (GTK-settings) to apply the icon theme

Reboot:
```bash
sudo reboot
```
---

## ⚙️ Further configurations
- [hyprland](https://wiki.hyprland.org/Configuring/) – add commands to excecute at start, understand the keybinds or add custom keybinds, etc.
- [neofetch](https://github.com/dylanaraps/neofetch) – Change image_source (line 743) in config to point to your image, or you can use mine I dont mind 😋.
- [hyprpaper](https://wiki.hyprland.org/Hypr-Ecosystem/hyprpaper/) - change config to point to your wallpaper.
- [waybar](https://github.com/Alexays/Waybar) - Thanks to [mechabar](https://github.com/sejjy/mechabar) for letting me *cough cough borrow* their setup.

click on the hyperlinks for docs relating to the respective configurations.

## ⌨️ General Keybinds
| Package                          | Description                                                                  |
|----------------------------------|------------------------------------------------------------------------------|
| **WIN+F**                        | fullscreen windows                                                           |
| **WIN+shift+Q**                  | close window                                                                 |
| **Win+shift+E**                  | leave hyprland and go back to greeter (log out)                              |
| **WIN+left_click**               | drag windows                                                                 |
| **WIN+right_click**              | resize windows                                                               |  
| **WIN+tab**                      | enable window float                                                          |
| **WIN+E**                        | launch Thunar                                                                |
| **WIN+R**                        | launch Wofi search                                                           |
| **WIN+1,2,3,4,5,...**            | switch workspace                                                             |
| **PrtSc**                        | screenshot (check config to set screenshot save location)                    |
