# | Dotfiles (unorganized) | W.I.P. btw |

My configuration files for quite a few stuff, including, but not limited to: [WezTerm](https://github.com/wez/wezterm), [fish](https://fishshell.com) and [Starship](https://starship.rs/).

You can download the files using [this tool by minhaskamal](https://minhaskamal.github.io/DownGit/).

## No Install scripts, because I do not know how to make those lol.



(NOTE: these configs are done on an Arch Linux machine, so if you use a different distro, check the Credits (by scrolling to the very bottom), You will be redirected to one of the program's homepage.

# -- TERMINAL --
## Installing WezTerm, fish and starship:

run `sudo pacman -S fish starship | yay -S wezterm-git`

then run the following 2 commands, to make fish the default shell:

`echo /usr/bin/fish | sudo tee -a /etc/shells.`

then:

`chsh -s /usr/bin/fish`

restart your terminal, you should get a greeting message like this:

![greeting](https://user-images.githubusercontent.com/86793541/230217834-e80441af-f958-4ccc-b100-91bd2b5b0aa1.png)

If not, run the command `echo $SHELL`. You should get the following output.

![output](https://user-images.githubusercontent.com/86793541/230218707-c62eeaa5-78cf-492c-a5e6-8fc8cc27a26c.png), 

If not, search how to make fish the default shell on your search engine idk.

# Configuring the stuff:

## For WezTerm: copy the [config file](https://github.com/C7DE/arch-linux-dotfiles/blob/main/wezterm/wezterm.lua) to `/home/USER/.config/wezterm/`

You can do this manually (below), or by running this command:

`sudo cp /home/USER/Downloads/wezterm.lua ~/.config/wezterm`

MANUALLY: If you couldn't download the file, create a file called `wezterm.lua` in the WezTerm config folder, copy the contents of my wezterm.lua file, and paste it into the newly created file. Sounds confusing, because I'm too stupid to explain it properly.

## For fish, you can just add the following string to the bottom of the file:

`starship init fish | source`

This will make sure that Starship starts, everytime you open a fish terminal

## For Starship, it's similar to the WezTerm configs: download the [starship.toml file](https://github.com/C7DE/arch-linux-dotfiles/blob/main/starship.toml), and put it in `~/.config`

Overwrite the existing `starship.toml` file, If there is any.

### Your Terminal should look like this after you're done with all that :)

![image](https://user-images.githubusercontent.com/86793541/230220382-67da92d9-fa16-4a65-b09d-6a2d46055938.png)

You can change the Arch logo with the logo of your choice, if it is available as a [Nerd Font](https://www.nerdfonts.com/) icon

# Credits:
[Starship](https://starship.rs/)

Starship config by someone on the Catppuccin Discord server. Not to be found on GitHub, sadly.

[WezTerm](wezfurlong.org/wezterm/)

[WezTerm GitHub page](https://github.com/wez/wezterm/)

[fish](https://fishshell.com/)

[minhaskamal for the GitHub file/directory downloading tool](https://minhaskamal.github.io/DownGit/)

And you!
