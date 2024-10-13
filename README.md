# My Dotfiles

This repository contains dotfiles for my system, managed using GNU Stow.

## Requirements

Ensure you have the following installed on your system:

### Git

```bash
brew install git
```

### GNU Stow

```bash
brew install stow
```

## Installation

1. Clone this repository:

```bash
git clone https://github.com/yourusername/dotfiles.git ~/.dotfiles
cd ~/.dotfiles
```

2. Use GNU Stow to symlink the dotfiles:

```bash
stow */
```

This command will symlink all directories in the `~/.dotfiles` folder to your home directory.

To stow specific configurations, use:

```bash
stow zsh
stow vim
# ... etc.
```

## Using stow --adopt

The `--adopt` flag in GNU Stow is particularly useful when you're setting up your dotfiles on a new system or incorporating existing configuration files into your dotfiles repository. Here's how to use it:

```bash
stow --adopt */
```

This command will:
1. Move any existing files in your home directory that conflict with your dotfiles into your dotfiles directory.
2. Create symlinks from your dotfiles directory to your home directory.

This is helpful because:
- It preserves your existing configurations.
- It automatically incorporates your current setup into your dotfiles repository.
- It prevents conflicts between existing files and your dotfiles.

**Note:** Be careful when using `--adopt` as it will overwrite files in your dotfiles directory. It's a good idea to backup your dotfiles repository before using this option.

## Included Configurations

- `zsh/`: ZSH configuration files
- `vim/`: Vim configuration files
- `git/`: Git configuration files
- // ... Add other configuration directories as needed

## Customization

Feel free to modify any of the dotfiles to suit your needs. After making changes, you can restow the affected configurations:

```bash
stow -R zsh
```

## Uninstalling

To remove the symlinks for a specific configuration:

```bash
stow -D zsh
```

To remove all symlinks:

```bash
stow -D */
```

## Updating

To update your dotfiles:

1. Pull the latest changes:

```bash
cd ~/.dotfiles
git pull origin main
```

2. Restow the configurations:

```bash
stow -R */
```

## Contributing

If you'd like to contribute to these dotfiles, please fork the repository and create a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
