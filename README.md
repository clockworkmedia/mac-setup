# mac-setup
Steps for setting up your Macbook for front-end web development (macOS Sierra v. 10.12 Setup)

[View a more detailed explanation of these steps here.](https://www.taniarascia.com/setting-up-a-brand-new-mac-for-development/)

## Preferences

- **Keyboard > Text >** Disable "Correct spelling automatically".
- **Security and Privacy > Firewall >** On
- **Security and Privacy > General >** App Store and identified developers
- **File Sharing >** Off
- **Users & Groups > Login Items >** Spectacle, Flux

### Show Library folder

```shell
chflags nohidden ~/Library
```

### Show hidden files

This can also be done by pressing `command` + `shift` + `.`.

```shell
defaults write com.apple.finder AppleShowAllFiles YES
```

### Show path bar

```shell
defaults write com.apple.finder ShowPathbar -bool true
```

### Show status bar

```shell
defaults write com.apple.finder ShowStatusBar -bool true
```

## Homebrew

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Mac App Store

```shell
brew install mas
```

#### Sign in

```shell
mas signin email@email.com
```

### Brewfile

```shell
touch Brewfile
```

```shell
tap 'caskroom/cask'

# Basic Brew brew 'git'
brew 'node'
brew 'npm'
brew 'docker'
brew 'docker-machine'
brew 'antigen'  # Development
cask 'java'
cask 'virtualbox'
cask 'vagrant'
cask 'vagrant-manager'
cask 'iterm2'
cask 'sequel-pro'
cask 'postman'
cask 'sourcetree'
cask 'visual-studio-code'
brew 'awscli'

# Web Development
brew 'php70-xdebug'
brew 'composer'
brew 'php-cs-fixer'
brew 'yarn'
cask 'medis'
cask 'sequel-pro'

# Mobile dev
cask 'android-studio'
cask 'genymotion'
cask 'fastlane'

# applications
cask 'slack'
cask 'vlc'
cask 'clipmenu'
cask 'skype'
cask 'teamviewer'
cask 'google-chrome'
cask 'firefox'
cask 'opera'
cask 'dropbox'
cask 'filezilla'

mas 'Slack', id: 803453959
```

## GitHub

### Config - `~/.gitconfig`


```shell
[user]
	name = First Last
	email = email@email.com
[github]
	user = username
[alias]
	a = add
	ca = commit -a
	cam = commit -am
	s = status
	pom = push origin master
	pog = push origin gh-pages
	puom = pull origin master
	puog = pull origin gh-pages
	cob = checkout -b
[credential]
	helper = osxkeychain
```


## SSH

### Config - `~./ssh/config`

```shell
Host example
    HostName example.com
    User example-user
    IdentityFile key.pem
```

### Generate SSH key

```shell
ssh-keygen -t rsa -b 4096 -C "email@email.com"
```

## Bash

### Config - `~/.bash_profile`

```shell
alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor'
```

```shell
source ~/.bash_profile
```

## Node Package Manager

### Gulp

```shell
npm install --global gulp-cli
```

---

Contributing
======

Please read the [contribution guidelines] before submitting a pull request.

In particular: <strong>If you have commit access, please don't merge changes without
waiting a week for everybody to leave feedback.</strong>

[contribution guidelines]: ../../../contributing

Maintainers
======

![clockwork](http://apps.clockworkmedia.co.za/github/assets/logos/logo.png)

This repository is maintained by [Clockwork Media](//www.clockworkmedia.co.za).

