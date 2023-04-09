# Trash af dotfiles
## This is a guide on getting a stupid, goofy rice, like mine (Go to #Preview). I will work on it later. Desktop Environment is KDE Plasma.

# Table of Content or smth:
1. [Preview](#preview)
2. [Installation](#install)
3. [Installing on Arch or Arch based Distros](#arch)
4. [Installing on Debian or Debian based Distros](#debian)


5. [WezTerm (Debian)](#wezterm-debian)
6. [Picom (Debian)](#picom-debian)
7. [fish (Debian)](#fish-debian)
8. [Starship (Debian)](#starship-debian)

9. [Setting picom up](#picom-setup)
10. [Installing the Starship theme on WezTerm](#starship-config)
11. [Rounded and Centered Panel](#rounded-panel)
12. MORE COMING SOON, maybe.

<a id="preview"></a>
## Preview

![image](https://user-images.githubusercontent.com/86793541/230784886-9422a41e-af54-4a9f-b5cb-96156a1de280.png)


<a id="install"></a>

## Installation of the dependencies:

<a id="arch"></a>

### On Arch Linux/Arch based Distros:
```sh
sudo pacman -Syu fish starship && yay -Sy picom-ibhagwan-git wezterm
```
<a id="debian"></a>

### On Debian or other Distros based on Debian:

<a id="wezterm-debian"></a>

#### WezTerm:

```sh 
curl -LO https://github.com/wez/wezterm/releases/download/20230408-112425-69ae8472/wezterm-20230408-112425-69ae8472.Ubuntu20.04.deb

sudo apt update && sudo apt upgrade

sudo apt install -y ./wezterm-20230408-112425-69ae8472.Ubuntu20.04.deb
```
<a id="picom-debian"></a>
#### picom
```sh
    sudo apt update && sudo apt upgrade
    
    sudo apt install libxext-dev libxcb1-dev libxcb-damage0-dev libxcb-xfixes0-dev libxcb-shape0-dev libxcb-render-util0-dev libxcb-render0-dev libxcb-randr0-dev libxcb-composite0-dev libxcb-image0-dev libxcb-present-dev libxcb-xinerama0-dev libpixman-1-dev libdbus-1-dev libconfig-dev libgl1-mesa-dev  libpcre2-dev  libevdev-dev uthash-dev libev-dev libx11-xcb-dev
    cd /tmp
    git clone https://github.com/ibhagwan/picom.git && cd picom
    git submodule update --init --recursive
    meson --buildtype=release . build
    ninja -C build
    ninja -C build install #Run it with sudo if it fails
```
<a id="fish-debian"></a>
### fish shell
```sh
sudo apt-add-repository ppa:fish-shell/release-3
sudo apt update
sudo apt install fish
```
<a id="starship-debian"></a>
```sh 
curl -sS https://starship.rs/install.sh | sh

#Add `starship init fish | source` to the end of `~/.config/fish/config.fish`
```    

<a id="picom-setup"></a>
## Setting picom up:
First of all, make sure that you've installed picom. 
If you did install it, open Settings, go to System and Monitor >> Compositor.
Here, disable `Enable on startup`

![image](https://user-images.githubusercontent.com/86793541/230785020-cb1129e8-844c-44de-99e2-138f23a68afe.png)

Then log out, then back in.
After logging back in, run this command:
```sh
curl https://raw.githubusercontent.com/deltaBTW/dotfiles/main/picom/picom.conf -o ~/.config/picom.conf
```

Now run picom. 

![image](https://user-images.githubusercontent.com/86793541/230785309-aa382a7f-8d67-4ad1-976d-9d38e6910624.png)

You should get rounded window corners like in the screenshot (not really visible, blame my dark background).

To make picom start automatically when you log in, run 

`mkdir -p ~/bin/ && echo "picom &" > ~/bin/autostart.sh && chmod +x ~/bin/autostart.sh`

and add ~/bin/autostart.sh to the Autostart entry in the Settings.

To do that, open Settings >> Startup and Shutdown >> Autostart >> Add... >> Add Login script, and choose autostart.sh in the ~/bin folder.

Picom should start automatically on every login now.

<a id="starship-install"></a>
## Starship config
Run this command: 
```sh 
curl https://raw.githubusercontent.com/deltaBTW/dotfiles/main/starship/starship.toml -o ~/.config
```
If there already is a starship config file, delete it first.
Restart the terminal.

<a id="rounded-panel"></a>
## Rounded, Centered Panel.
Right click on the panel, and click `Enter Edit mode`

Then click on `More options`, and choose "Center"
![image](https://user-images.githubusercontent.com/86793541/230786334-352e5146-3d6b-4b90-a120-e215bca72d40.png)

Now drag on one of these arrows to adjust the size:
![image](https://user-images.githubusercontent.com/86793541/230786381-9a9cfa81-5fb7-44fb-a671-e238c6dee6ed.png)

Now you have a centered panel, and should be rounded if you installed the picom fork by ibhagwan.





# CREDITS
#### [vista1nik](https://reddit.com/u/vista1nik) picom config
