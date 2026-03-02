# `nd`

Have you ever found yourself constantly doing `ls cd ls cd ls cd`? Well have I
got a solution for you!

Rather than using something like `cd $(fzf)` where you have to manually search
for the directory, this tool works off of numbering and progressively revealing layers
of directories.

```bash
Path: /current/working/dir
Commands: [1..3] select, [b] back, [q] quit

┃ 1. src
┃ 2. docs
┃ 3. target
>
```

## Installation

```bash
cargo install nd-cli
```

### Setup shell

Run the following command for your shell, this will add the `nd` command to
your config allowing you to navigate to the directory after quitting.

```bash
# zsh
echo 'eval "$(nd-cli init zsh)"' >> ~/.zshrc
source ~/.zshrc

# bash
echo 'eval "$(nd-cli init bash)"' >> ~/.bashrc
source ~/.bashrc

# fish
echo 'nd-cli init fish | source' >> ~/.config/fish/config.fish
source ~/.config/fish/config.fish

# powershell
Add-Content -Path $PROFILE -Value 'Invoke-Expression (& nd init powershell)'
. $PROFILE
```

## Usage

```bash
nd
```

**Commands**:

- `1..N` select a directory
- `b` go to parent directory
- `q` quit and print selected path

**Flags**:

- `--show-hidden` include directories that start with `.`
- `--start-dir <PATH>` start browsing from a specific directory
- `--no-color` disable ANSI color output
