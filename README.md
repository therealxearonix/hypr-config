# My Hyprland Dotfiles
Just my configuration for hyprland. You can customize it as you want.
The sky's the limit!
## Requirements
### Essential
- Hyprland (ofc)
- Wofi (app launcher)
- Kitty (terminal emulator)
- Waybar
- Hyprpaper (wallpapers)
### Optional
- Hyprlock (lock screen)
- Hyprshot (screenshots)
- Wlogout
- Fastfetch
- Greetd with nwg-hello (login manager)
## Installation
1. Backup your existing configuration somewhere (optional, skip if you are installing this for first time):
```
mv ~/.config/hypr ~/hypr-backup
```

2. Clone this repo:
```
git clone https://github.com/therealxearonix/hypr-config.git ~/.config
```

3. Install dependencies (example for arch linux):
```
yay -S hyprland waybar wofi kitty hyprlock hyprpaper hyprshot wlogout fastfetch greetd nwg-hello
```

4. And finally start Hyprland!
```
Hyprland
```

## Post installation
### Login manager
Config for greetd (nwg-hello) should be in `/etc` directory, so move it here:
```
mv ~/.config/greetd /etc
```

Enable `greetd.service` so it will start at boot:
```
systemctl enable greetd.service
```
## Key bindings
**Main bindings:**
- `SUPER + Left Alt` – launch terminal
- `SUPER + C` – close window
- `SUPER + X` – lock screen
- `SUPER + A` – app launcher
- `SUPER + Q` – launch browser
- `SUPER + F` – open file manager

**Window management:**
- `SUPER + Arrows` – move focus
- `SUPER + Shift + Arrows` – resize windows
- `SUPER + [1-9]` – switch workspaces
- `SUPER + Left Mouse` – move windows

**Screenshots:**
- `Print` – screenshot area
## Customization
### Main Hyprland config
All settings mentioned in this section are defined in the `hyprland.conf`
#### Default programs
You can set programs as default to use them in keybindings and etc:
```
$terminal = kitty
$fileManager = thunar
$browser = firefox
```
#### Keybindings
Create keybindings like this (example):
```
bind = $mainMod, Q, exec, $browser # launch browser
bind = $mainMod, X, exec, hyprlock # lock screen
bind = $mainMod, C, killactive # close active window
```

`$mainMod` defines some key as main modifier (by default its "Win" key)
You can change it to other key if you want it tho.
#### Displays
Edit these settings to match your display(s) config:
```
monitor=eDP-1,1920x1080@60,-1920x0,1
monitor=HDMI-A-1,1920x1080@60,0x0,1
```
### Wallpapers
You can change the wallpapers and its locations in `hyprpaper.conf`:
```
preload=/home/<username>/wallpapers/w1.jpg
preload=/home/<username>/wallpapers/w2.jpg

wallpaper=eDP-1,/home/<username>/wallpapers/w1.jpg
wallpaper=HDMI-A-1,/home/<username>/wallpapers/w2.jpg
```
## Troubleshooting
**Icons not showing up on waybar**
- You need to install font Awesome and any Nerd font from [here](https://www.nerdfonts.com/font-downloads) or from your linux distribution repo (example for arch linux):
```
pacman -S nerd-fonts otf-font-awesome
```

---
Yeah, this description might feel kinda off right now, but it's just a start. I'll keep improving it.

So I might forget to mention something. If you have any suggestions for improvement, found any mistakes or something just doesn't work as described here, please write to Issues.
