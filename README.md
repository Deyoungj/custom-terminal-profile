# Pixegami Terminal Profile

This is my profile for UNIX (MacOS/Linux) terminals. For Ubuntu, I just use the default terminal
app. For MacOS, I use [iTerm2](https://iterm2.com/).

> In the MacOS case, I have successfully installed this theme once before, but most of the terminal commands
> will be different. You'll just have to open the `.sh` files and figure out how to adapt it to MacOS
> until I can prepare MacOS commands.

# Prerequisites

For the scripts to work, I think these are the bare minimum requirements.

```bash
# Update your software repositories.
sudo apt-get update
sudo apt-get upgrade

# Install Git.
sudo apt-get install -y git

# Install Vim.
sudo apt-get install -y vim
```

# Installation

### Powerline (and fonts)

First, we'll install the font (RobotoMono for Powerline). I'll also install it into VIM, since that
is my built-in editor of choice (but you don't have to use it).

The Powerline fonts also include special characters (like Git branches) that we will use later in
the terminal profile theme.

```bash
./install_powerline.sh
```

### ZSH, OhMyZSH and Plugins

The shell that I use is "ZSH", with the OhMyZSH upgrade on top of that. To install all of that stuff,
you can run the helper script (and may need to restart after).

```bash
./install_terminal.sh
```

This script will also install two plugins that I like to use: auto-complete and color highlighting.

```bash
# You don't need to execute this - it's part of the script already.
(cd ~/.oh-my-zsh/custom/plugins && git clone https://github.com/zsh-users/zsh-syntax-highlighting)
(cd ~/.oh-my-zsh/custom/plugins && git clone https://github.com/zsh-users/zsh-autosuggestions)
```

And finally it will also copy over the `.zshrc` and `pixegami-agnoster.zsh-theme` files for the
terminal to use (which will wire up the plugins and the theme).

If it looks funky after this command, then you might need to wait until the theme is updated with a
Powerline font (the next step), and may need to also restart your machine.

### Profile (font and color)

The last command is to create a terminal profile that will set the colors and also set the font
to be the Powerline one we installed earlier (required for the theme to display correctly).

```bash
./install_profile_theme.sh
```

You can also change the font to any of the other [Powerline Patched Fonts](https://github.com/powerline/fonts) too if you don't like RobotoMono.


## Notes

How to dump current terminal profiles.

```bash
dconf dump /org/gnome/terminal/legacy/profiles:/ > gnome-terminal-profiles.dconf
```

How to display terminal information (I use [Neofetch](https://github.com/dylanaraps/neofetch)).

```bash
sudo apt-get install neofetch

# Display the profile
neofetch
```

## Sources

Here are some of the main resources I used as part of this terminal setup.

[Oh My Zsh!](https://medium.com/wearetheledger/oh-my-zsh-made-for-cli-lovers-installation-guide-3131ca5491fb) | [Robby Russel OMZ](https://github.com/robbyrussell/oh-my-zsh) | [Install Powerline](https://askubuntu.com/questions/283908/how-can-i-install-and-use-powerline-plugin) | [Powerline Patched Fonts](https://github.com/powerline/fonts)
| [Agnoster Theme](https://gist.github.com/3712874)

