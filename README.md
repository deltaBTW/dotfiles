# | Dotfiles |

My configuration files for quite a few stuff, including, but not limited to: [WezTerm](https://github.com/wez/wezterm), [fish](https://fishshell.com) and [Starship](https://starship.rs/).

## No Install scripts, because I do not know how to make those lol.

W.I.P. btw

(NOTE: these configs are done on an Arch Linux machine, so if you use a different distro, click on the link below each dependency for an Install Guide, for other distros aswell.



# -- TERMINAL --
## Installing WezTerm:

[Installation Guide for any other distro](https://wezfurlong.org/wezterm/install/linux.html)

Here, I'm gonna assume that you're using `yay`, of course, you can replace yay with your AUR helper.

run `yay -S wezterm-git`

## Installing fish:

[Installation Guide for any other distro](https://fishshell.com/)

run `sudo pacman -S fish`

then run the following 2 commands:

`echo /usr/bin/fish | sudo tee -a /etc/shells.`

then:

`chsh -s /usr/bin/fish`

restart your terminal, you should get a greeting message like this:

![greeting](https://user-images.githubusercontent.com/86793541/230217834-e80441af-f958-4ccc-b100-91bd2b5b0aa1.png)

If not, run the command `echo $SHELL`. If you don't get this output 

![output](https://user-images.githubusercontent.com/86793541/230218707-c62eeaa5-78cf-492c-a5e6-8fc8cc27a26c.png), 

Then I don't know, [Take a look at this page, or browse through the whole Documentation](https://fishshell.com/docs/current/index.html#installation)


## Installing Starship:

`sudo pacman -S starship`

OR, for any other distro: 

`curl -sS https://starship.rs/install.sh | sh`

### Configuring the stuff:

#### For WezTerm: copy the [config file](https://github.com/C7DE/arch-linux-dotfiles/blob/main/wezterm/wezterm.lua) to `/home/USER/.config/wezterm/`

You can do this manually, or by running this command:

`sudo cp /home/USER/Downloads/wezterm.lua ~/.config/wezterm`

If you couldn't download the file, create a file called `wezterm.lua` in the WezTerm config folder, copy the contents of my wezterm.lua file, and paste it into the newly created file. Sounds confusing, because I'm too stupid to explain it properly.

#### For fish, you can just add the following string to the bottom of the file:

`starship init fish | source`

This will make sure that Starship starts, everytime you open a fish terminal

#### For Starship, it's similar to the WezTerm configs: copy the downloaded [starship.toml file](https://github.com/C7DE/arch-linux-dotfiles/blob/main/starship.toml), and put it in `~/.config`

Overwrite the existing `starship.toml` file, If there is any.

Your Terminal should look like this after you're done with all that :)

![image](https://user-images.githubusercontent.com/86793541/230220382-67da92d9-fa16-4a65-b09d-6a2d46055938.png)


# Credits:
[Starship](https://starship.rs)

Starship config by someone on the Catppuccin Discord server. Not to be found on GitHub, sadly.

[WezTerm](wezfurlong.org/wezterm)

[WezTerm GitHub page](https://github.com/wez/wezterm)

[fish](https://fishshell.com/)

And you!
