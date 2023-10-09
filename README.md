# .dotfiles
My dotfiles for [Prasanthrangan's hyprdots](https://github.com/prasanthrangan/hyprdots)

## Steps to bootstrap a new hyprdots install

1. Clone this repo.

```zsh
# Use SSH (if set up)...
git clone https://github.com/topazrn/.dotfiles

# ...or use HTTPS and switch remotes later.
git clone https://github.com/topazrn/.dotfiles
```


2. Create symlinks in the Home directory to the real files in the repo.

```zsh
# There are better and less manual ways to do this;
# investigate install scripts and bootstrapping tools.

cd .dotfiles
ln -s ./.gitconfig ~/.gitconfig
ln -s ./.zshrc ~/.zshrc
ln -s ./.config/hypr/keybindings.conf ~/.config/hypr/keybindings.conf
ln -s ./.config/hypr/monitors.conf ~/.config/hypr/monitors.conf
ln -s ./.config/hypr/userprefs.conf ~/.config/hypr/userprefs.conf
ln -s ./.config/hypr/windowrules.conf ~/.config/hypr/windowrules.conf
```


3. Install softwares listed in `pacman.dump`.

```zsh
# These could also be in an install script.

# Then pass in the pacman.dump location...
yay -S $(cat ./pacman.dump | cut -d' ' -f1)

# In case I forgot how to generate pacman.dump:
yay -Qe > .dotfiles/pacman.dump
```


## TODO List

- Organize these growing steps into multiple script files.
- Automate symlinking and run script files with a bootstrapping tool like [Dotbot](https://github.com/anishathalye/dotbot).
- Make a checklist of steps to decommission your computer before wiping your hard drive.
- Find inspiration and examples in other Dotfiles repositories at [dotfiles.github.io](https://dotfiles.github.io/).
- And last, but hopefully not least, take this course, [**Dotfiles from Start to Finish-ish**](https://www.udemy.com/course/dotfiles-from-start-to-finish-ish/?referralCode=445BE0B541C48FE85276 "Learn Dotfiles from Start to Finish-ish on Udemy"
)!