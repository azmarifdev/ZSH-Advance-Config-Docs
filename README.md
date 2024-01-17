# Install ZSH on Linux and make it your default Shell
Bash (Bourne Again Shell) is the default command-line shell on many distributions. Zsh (Z Shell) is a powerful shell that operates as both an interactive shell and as a scripting language interpreter.

# 🚀 Installation
## 1. Install the zsh package:
- #### Ubuntu/Mint:
```
sudo apt install zsh
```
- #### Fedora:
```
sudo dnf install zsh
```
- #### Manjaro/Arch:
```
sudo pacman -S zsh
```

For basic configuration run the following command:
```
zsh /usr/share/zsh/functions/Newuser/zsh-newuser-install -f
```
Follow the recommended options, save and exit.

## 2. Oh-My-Zsh & plugins

Now, let’s install a powerful additional program.

```zsh```, ```curl``` and ```git``` should be installed first.

#### First, install curl & git:
- Ubuntu/Mint:
```
sudo apt install curl git
```
- Fedora:
```
sudo dnf install curl git
```
- Manjaro/Arch:
```
sudo pacman -S curl git
```

#### Then install ```oh-my-zsh```:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
I recommend installing 6 additional plugins that we’ll activate later through OMZ configuration file

- #### zsh-syntax-highlighting
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

- #### zsh-autosuggestions
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

- #### zsh-Z
```
git clone https://github.com/agkozak/zsh-z $ZSH_CUSTOM/plugins/zsh-z
```

- #### zsh-fast-syntax-highlighting
```
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
```

- #### zsh-autocomplete
```
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git $ZSH_CUSTOM/plugins/zsh-autocomplete
```

- #### fzf
```
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
```
```
~/.fzf/install
```

## 3. Configuring Zsh

For advanced configuration, modify the ```~./zshrc``` config file.

Follow this instraction for Configuring zsh:

1. Open ```~./zshrc``` file.
```
nano ~/.zshrc
```

2. Find the line which says ```plugins=(git)```.
Replace that line with:
```
plugins=(
    fzf
    git
    sudo
    history-substring-search
    colored-man-pages
    zsh-autosuggestions
    zsh-syntax-highlighting
    fast-syntax-highlighting
    zsh-autocomplete
    zsh-z
)
```

3. Find the ```ZSH_THEME="robbyrussell"```
Replace with ```ZSH_THEME="gnzh"```


- #### Tip: Apply the changes without needing to logout and then back in by running ```source ~/.zshrc```.
```
source ~/.zshrc
```

## 4. Make Zsh default
```
chsh -s $(which zsh)
```

#### You can find my fork of the file on [Github Gists](https://gist.github.com/azmarifdev/9c16c5a33e93aee05b35147fe7da1015)

Enjoy!
