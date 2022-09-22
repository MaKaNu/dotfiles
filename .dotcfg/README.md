# SETUP[^1]

``` bash
git init --bare $HOME/.dotcfg
alias dotcfg='git --git-dir=$HOME/.dotcfg/ --work-tree=$HOME'
dotcfg branch -M main
dotcfg config status.showUntrackedFiles no
dotcfg remote add origin git@github.com:MaKaNu/dotfiles.git
```
Create an empty Repository on your desired hosting service.

```bash
echo ".dotcfg" >> .gitignore
dotcfg add .gitigonre
dotcfg commit -m "Add .gitignore"
dotcfg push -u origin main
```

## Set alias permanantly
- bash: `echo "alias dotcfg='git --git-dir=$HOME/.dotcfg/ --work-tree=$HOME'" >> .bashrc`
- zsh: `echo "alias dotcfg='git --git-dir=$HOME/.dotcfg/ --work-tree=$HOME'" >> .zshrc`
- fish: `alias --save dotcfg='git --git-dir=$HOME/.dotcfg/ --work-tree=$HOME'`


# Reproduction

```bash
alias dotcfg='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
git clone --bare <git-repo-url> $HOME/.dotcfg
dotcfg checkout
```
>The last command might turn into an error because a few files/directories already exists. Backup those listed or remove them and repeat the command.

```bash
dotcfg config --local status.showUntrackedFiles no
```


# Usage
```bash
dotcfg status
dotcfg add .vimrc
dotcfg commit -m "Add vimrc"
dotcfg add .bashrc
dotcfg commit -m "Add bashrc"
dotcfg push
```

[^1]: Based on: https://www.atlassian.com/git/tutorials/dotfiles
