# Dotfiles

Cross-platform dotfiles managed by [chezmoi](https://chezmoi.io).

## 🚀 Quick Setup

### Ubuntu/Debian VM or Server

```bash
# Install chezmoi + apply dotfiles
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply {{github_username}}

# Install packages (eza, ripgrep, lazygit, neovim, starship)
# This runs automatically via run_once script
```

### macOS

```bash
# Install chezmoi
brew install chezmoi

# Apply dotfiles
chezmoi init --apply {{github_username}}
```

## 📦 What's Included

### Configurations
- `.zshrc` - macOS shell config (zim framework)
- `.bashrc` - Ubuntu/Linux shell config (appends to existing)
- `.gitconfig` - Git configuration
- `nvim/` - Neovim setup (LazyVim)
- `gh/` - GitHub CLI config
- `ghostty/` - Ghostty terminal config
- `zed/` - Zed editor settings

### Ubuntu Auto-Install
Script automatically installs:
- **ripgrep** - Fast search tool
- **eza** - Modern `ls` replacement
- **bat** - Better `cat` with syntax highlighting
- **lazygit** - Terminal UI for git
- **neovim** - Latest stable
- **starship** - Cross-shell prompt

## 🔧 Common Workflows

### Update dotfiles
```bash
chezmoi edit ~/.bashrc    # Edit in chezmoi
chezmoi diff              # Preview changes
chezmoi apply             # Apply to ~
```

### Commit changes
```bash
chezmoi cd                # Navigate to repo
git add .
git commit -m "update"
git push
```

### Pull updates on other machines
```bash
chezmoi update
```

## 🎯 Key Features

- **Cross-platform** - Separate configs for macOS (zsh) and Linux (bash)
- **Template-based** - Only applies Linux configs on Linux systems
- **Auto-setup** - Run-once scripts handle package installation
- **Append-friendly** - `.bashrc` appends to Ubuntu defaults

## 📝 Notes

- Ubuntu `.bashrc` only applies on Linux (`chezmoi` templates)
- Package install script runs once per machine
- Private configs (like `gh`) are tracked but may need manual setup
