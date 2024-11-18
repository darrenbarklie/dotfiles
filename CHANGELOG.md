# dotINSTALL

## 2024-11-12

### Brew

- `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
- `echo >> /Users/daz/.zprofile`
- `echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/daz/.zprofile`
- `eval "$(/opt/homebrew/bin/brew shellenv)"`
- Ref: https://docs.brew.sh/FAQ#how-do-i-update-my-local-packages

### iTerm2

- `brew install --cask iterm2`

### NeoVim

- `brew install neovim` 

### Firefox

- `brew install --cask firefox`
- Add extension ClearnURLs
- Add extension Facebook Container
- Add extension Privacy Badger
- Add extension uBlock Origin

### Google Chrome

- `brew install --cask google-chrome`

### NVM & NodeJS

_NOTE_: Retired for fnm

- `brew install nvm`
- Create `~/.zshrc` and add following script:
    ```zsh
    export NVM_DIR="$HOME/.nvm"
    [ -s "$HOMEBREW_PREFIX/opt/nvm/nvm.sh" ] && \.
    "$HOMEBREW_PREFIX/opt/nvm/nvm.sh"
    [ -s "$HOMEBREW_PREFIX/opt/nvm/etc/bash_completion.d/nvm" ] && \.
    "$HOMEBREW_PREFIX/opt/nvm/etc/bash_completion.d/nvm"
    ```
- `nvm install 22`
- `nvm run 22`
- `node --version`
- `npm --version`

### PNPM

- `brew install pnpm`
- `pnpm --version`

### Git

- `brew install git`
- `git --version`
- Generate a [new SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key)
- `ssh-keygen -t ed25519 -C "darrenbarklie@gmail.com"`
- Create .ssh/id_ed25519 public and private key
- Add SSH key to the ssh-client with `eval "$(ssh-agent -s)"`
- Create .ssh/config file and add:
```zsh
    Host github.com
      AddKeysToAgent yes
      UseKeychain yes
      IdentityFile ~/.ssh/id_ed25519
```
- `ssh-add --apple-use-keychain ~/.ssh/id_ed25519`
- Add a [SSH key to GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)


## 2024-11-13

### fnm

- Discovered that nvm is slowing down terminal initialisation
- `brew uninstall nvm` removes nvm and node
- `brew install fnm`
- `fnm completions --shell zsh`
- Add to .zshrc `eval "$(fnm env --use-on-cd --shell zsh --version-file-strategy=recursive)"`
- `fnm install 22`
- `node -v`
- `npm -v`


### Nerd Font: 

- Select from [Nerd Fonts Downloads](https://www.nerdfonts.com/font-downloads)
- 0xProto Nerd Font

### Starship

- `brew install starship`
- Add to .zshrc `eval "$(starship init zsh)"`
- `mkdir -p ~/.config && touch ~/.config/starship.toml`

### ZSH Autosuggestions

- `brew install zsh-autosuggestions`
- Add to .zshrc `source $(brew --prefix)/share/zsh-autosuggestions/zsh-autosuggestions.zsh`

### Neovim Configuration

- Ref: [How I Setup Neovim 2024: Video Tutorial](https://www.youtube.com/watch?v=6pAG3BHurdM)
- Ref: [How I Setup Neovim 2024: Blog Post](https://www.josean.com/posts/how-to-setup-neovim-2024)
- `brew install ripgrep` 

### Stats

- `brew install stats`

## 2024-11-14

### OBS

- `brew install obs`

### Spotify

- `brew install spotify`

### Chezmoi

- `brew install chezmoi`
- `chezmoi init`
- `cd ~/.local/share/chezmoi/`
- `chezmoi add ~/.zshrc` to create `~/.local/share/chezmoi/dot_zshrc`
- Edit dot_zshrc, run `chezmoi diff` to track diffs
- `chezmoi -n -v apply` to dry run update
- `chezmoi -v apply` to apply update
- `chezmoi cd`
- `git add .`
- `git commit -m "Initial commit"`
- `git push -u origin main`

### Zed

- `brew install --cask zed`

### Postman"

- `brew install --cask postman`

### Laravel Herd

- `brew install --cask herd`

### WP CLI

- `brew install wp-cli`
- `wp --info`
- `wp core download --path=~/Users/daz/Herd/projectname`
- `wp config create --dbname=projectname --dbuser=root --dbpass='' --dbhost=127.0.0.1`
- `wp db create`

### DBngin

- `brew install --cask dbngin`

### MySQL Client

- `brew install mysql-client`
- Add to .zshrc `export PATH="/opt/homebrew/opt/mysql-client/bin:$PATH"`

### Expo / Expo Orbit

- `brew install expo-orbit`
- `pnpm add --global eas-cli`


## Todo

- [Aerospace](https://nikitabobko.github.io/AeroSpace/guide)
