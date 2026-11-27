# My Dotfiles

> This directory contains the dotfiles for my system A clean, reproducible, and powered by **GNU Stow**.

---


## Requirements

On a fresh Arch Linux installation, run this command to install all necessary tools, fonts, and terminal utilities:
```sh
sudo pacman -S --needed git zsh alacritty stow fzf zoxide ttf-jetbrains-mono-nerd micro tree
```
---

## Repository Structure
```text
~/dotfiles
├── .config/
│   └── alacritty/
│       └── alacritty.toml  # Terminal aesthetics, fonts, and colors
├── .zshrc                  # Zsh plugins (Zinit), aliases, and shell integrations
└── README.md               # Setup documentation
```
---

## Installation

### 1. Clone the Repository
Clone your dotfiles into your home directory:
```
git clone git@github.com:iiBMT/dotfiles.git ~/dotfiles
cd ~/dotfiles
```
### 2. Symlink Configurations using GNU Stow
Use Stow to link configuration files back to `~`:
```sh
stow --adopt .
git restore .  # Clears any line-ending differences from stow adoption
```
### 3. Change Default Shell to Zsh
Set Zsh as your active default shell:
```sh
chsh -s $(which zsh)
```
Log out and log back in (or restart Alacritty) to complete the setup. Zinit will automatically install all missing Zsh plugins on the first launch.