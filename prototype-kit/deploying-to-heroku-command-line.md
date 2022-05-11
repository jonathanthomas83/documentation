# Manually deploying to Heroku using command line

This worked at DWP.

## Pre-requisites
- You have a local git repository, changes are saved and they are committed. Create a local git repository
- You have a Heroku account. Get a Heroku account
- You have a new application set up in Heroku. (In top right hand corner of Heroku go to new > create new app)
- (**Optional**) You have an SSH key added in Heroku. Managing SSH keys in Heroku
- You do not have access to any production environments.
- Your command line tools are up to date – **you can download the latest version form 'Self Service', search for "Xcode command line tools"**

## 1. Install Oh-my-ZSH

### a. Install

On the command line, 'cd' to home and type:

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### b. Edit .zshrc

In the finder, go to users/(your-name) and press 'command' + 'shift' +  '.' to
view hidden files.

Add the following to the top of the file:

```
export NODE_EXTRA_CA_CERTS=/etc/ssl/certs/ca-certs.pem
```

Add the following to the bottom of the file:

```
if [ -r "$HOME/.homebrew/" ]; then
    export PATH="$HOME/.homebrew/sbin:$HOME/.homebrew/bin:$PATH"

    #export readonly HOMEBREW_BOTTLE_DOMAIN="https://nexus.nonprod.dwpcloud.uk/repository/raw-homebrew/"
    export readonly HOMEBREW_NO_BOTTLE_SOURCE_FALLBACK=1
    export readonly HOMEBREW_NO_INSECURE_REDIRECT=1
    export readonly HOMEBREW_NO_ANALYTICS=1
    export readonly HOMEBREW_INSTALL_CLEANUP=1
    export readonly HOMEBREW_CASK_OPTS="--appdir=~/Applications"

    FPATH=$HOME/.homebrew/share/zsh/site-functions:$FPATH
fi
```
Save the file.

Close the Terminal and reopen it for the changes to take effect.

## 2. Install Homebrew

```
mkdir ~/.homebrew && curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C ~/.homebrew
```
**You may be prompted to update Command Line tools. Install from 'Self Service' or follow the instructions on the Terminal.**

Close the Terminal and reopen it for the changes to take effect.

## 3. Install Heroku CLI

```
brew tap heroku/brew && brew install heroku
```

Close the Terminal and reopen it for the changes to take effect.

## 4. Push to Heroku

```
heroku git:remote -a example-app
```

You'll see a message saying '*set git remote heroku to https://git.heroku.com/example-app.git*', confirming that the Heroku remote has been set up.

You may be asked to sign in to Heroku via the browser.

```
git push heroku master
```

## (Optional) Configure to push to GitHub and Heroku

See the following link:
https://gist.github.com/rvl/c3f156e117e22a25f242
