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

## 📦 Dependencies

Before using these configs, install the following packages:

```bash
sudo pacman -S --needed \
  alacritty gtk3 gtk4 hyprland mako neofetch \
  rofi-wayland waybar wofi \
  xdg-desktop-portal-hyprland brightnessctl playerctl \
  grim slurp swappy swaylock-effects \
  ttf-font-awesome ttf-nerd-fonts-symbols
