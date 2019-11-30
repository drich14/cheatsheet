# cheat-sheet

> Useful things I don't want to remember.


## Homebrew

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Cask

```
brew tap homebrew/cask
```

## Xcode Command Line Tools
xcode-select --install



## Crouton

### Install Xenial with LXDE and Xiwi

```
sudo sh ~/Downloads/crouton -t lxde,xiwi
```

### Start terminal in chroot

```
sudo startxiwi -n xenial -T xterm
```

### Start desktop environment

```
sudo startlxde
```

### More info

https://github.com/dnschneid/crouton/wiki/Crouton-Command-Cheat-Sheet


## zsh

### Install zsh

#### Ubuntu

```
sudo apt-get zsh

```

#### macOS

```
brew install zsh
```


### Install oh-my-zsh

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### Copy .zshrc

```
wget -P ~ https://raw.githubusercontent.com/drich14/cheatsheet/master/.zshrc
```


## Curl

```
sudo apt-get install curl
```

## wget

```
brew install wget
```

## Node Platform

### Install NVM

```
curl -sL https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh -o install_nvm.sh
bash install_nvm.sh
```

### Install latest Node (and NPM)

```
nvm install node
```

### Fix Ubuntu bug
```
ln -s /usr/bin/nodejs /usr/bin/node
```


## Yarn

### Ubuntu

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn
```

### macOS

```
brew install yarn --without-node
```


## Git

### Ubuntu

```
sudo apt-get install git
```

### macOS

```
brew install git
```


### Commitizen

#### Install Commitizen CLI (Globally) 

```
yarn global add commitizen
```

#### Install (in project root)

```
commitizen init cz-conventional-changelog --save-dev --save-exact
```


### GPG Auto Git Signing

#### Generate a new pgp key

```
gpg --gen-key
```

#### Check current keys

```
gpg --list-secret-keys --keyid-format LONG
```

#### Export public key in gpg
your_key_id is the HASH id in front of `sec` in previous command.

```
gpg --armor --export your_key_id | pbcopy
```

Paste on GitHub (https://github.com/settings/gpg/new)

#### Set a pgp key for git

```
git config --global user.signingkey your_key_id
git config --global commit.gpgsign true
```

#### These

~/.gnupg/gpg-agent.conf:
```
# Enables GPG to find gpg-agent
use-standard-socket

# Connects gpg-agent to the OSX keychain via the brew-installed
# pinentry program from GPGtools. This is the OSX 'magic sauce',
# allowing the gpg key's passphrase to be stored in the login
# keychain, enabling automatic key signing.
pinentry-program /usr/local/bin/pinentry-mac
```

~/.gnupg/gpg.conf:
```
# Uncomment within config (or add this line)
use-agent
```

Add this
```
touch ~/.gnupg/.gpg-agent-info
```

#### Git Flow

macOS
```
brew install git-flow
```

Ubuntu
```
apt-get install git-flow
```


## SSH

### Generate key

```
ssh-keygen -t rsa -b 4096 -C "dylanrichardson1996@gmail.com"
ssh-add -K ~/.ssh/id_rsa
pbcopy < ~/.ssh/id_rsa.pub
```

Paste on GitHub (https://github.com/settings/ssh/new)


## Heroku

```
brew install heroku-toolbelt
```


## Python

```
brew install python
pip3 install --upgrade pip setuptools wheel
brew install pyenv
```


## GUI Applications (macOS)

```
brew cask install qlstephen qlmarkdown quicklook-json quicklook-csv google-chrome appcleaner cheatsheet bettertouchtool docker dropbox 1password discord spotify gitkraken hyper homebrew/cask-versions/java8
```

