# RevolunixOS IDE

Opinionated Neovim launcher packaged with an AstroNvim-based configuration and
common development tools. It opens a file directly or starts Neovim with a
terminal and file tree when given a directory.

> [!WARNING]
> Every launch removes `~/.config/nvim` and replaces it with the configuration
> shipped by this package. It then runs recursive `chown` and `chmod` through
> `sudo`. Back up your Neovim configuration and inspect `src/ide` before use.

## Build

```bash
nix build github:RevolunixOS/pkg-ide
```

The wrapper adds Neovim, GNU Make, GNAT, Python, Node.js, bottom, ripgrep,
Lazygit, wl-clipboard, and the Nix language server to `PATH`.

## Usage

```bash
ide                 # open the current directory workflow
ide path/to/project # enter the directory, open terminal and file tree
ide path/to/file    # open one file
```

## Configuration

The packaged Neovim configuration lives under `src/nvim`. Because the launcher
copies it into the home directory at runtime, local edits in `~/.config/nvim`
are not persistent across launches.

## Development

```bash
git clone https://github.com/RevolunixOS/pkg-ide.git
cd pkg-ide
nix build
nix fmt
```

## License

See [`LICENSE`](LICENSE). Neovim plugins retain their own licenses.
