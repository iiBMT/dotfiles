# ⚡ BMT's Arch Linux Dotfiles

> A clean, reproducible, and Git-tracked terminal environment powered by **Zsh**, **Alacritty**, **Powerlevel10k**, and **GNU Stow**.

---


## 📦 Required Dependencies

On a fresh Arch Linux installation, run this command to install all necessary tools, fonts, and terminal utilities:

sudo pacman -S --needed git zsh alacritty stow fzf zoxide ttf-jetbrains-mono-nerd micro tree

---

## 📂 Repository Structure

~/dotfiles
├── .config/
│   └── alacritty/
│       └── alacritty.toml  # Terminal aesthetics, fonts, and colors
├── .zshrc                  # Zsh plugins (Zinit), aliases, and shell integrations
└── README.md               # Setup documentation

---

## 🚀 Fresh Installation & Restoration Walkthrough

### 1. Clone the Repository
Clone your dotfiles into your home directory:

git clone git@github.com:5g3a/dotfiles.git ~/dotfiles
cd ~/dotfiles

### 2. Symlink Configurations using GNU Stow
Use Stow to link configuration files back to `~`:

stow --adopt .
git restore .  # Clears any line-ending differences from stow adoption

### 3. Change Default Shell to Zsh
Set Zsh as your active default shell:

chsh -s $(which zsh)

Log out and log back in (or restart Alacritty) to complete the setup. Zinit will automatically install all missing Zsh plugins on the first launch.

---

## 🔄 Maintaining & Pushing Changes

Whenever you modify `~/.zshrc` or `~/.config/alacritty/alacritty.toml`, the changes reflect in your `~/dotfiles` repository automatically via symlinks.

To sync updates back to GitHub:

cd ~/dotfiles
git add .
git commit -m "Update dotfiles config"
git push