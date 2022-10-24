# New-Mac-Checklist: macOS Big Sur/Monterey/Ventura

A checklist I follow when setting up a new Mac's development environment.


## Checklist

### Prep OS X  
- Update OS
- Download and install latest version of Xcode from the Mac App Store. (if needed)
- Install Xcode Command Line Tools by running:

```
xcode-select --install
sleep 1
osascript <<EOD
  tell application "System Events"
    tell process "Install Command Line Developer Tools"
      keystroke return
      click button "Agree" of window "License Agreement"
    end tell
  end tell
EOD
```

### Show hidden files
- Run `defaults write com.apple.finder AppleShowAllFiles -boolean true; killall Finder`


### Setup dotfiles  
See [my dotfiles](https://github.com/ItsMeAra/dotfiles) 

During this process, you will setup your dotfiles, install global npm packages, and install [non Mac App Store apps](https://github.com/ItsMeAra/dotfiles/blob/master/brew-cask.txt) all via Homebrew. `#magic`


### Secure Git(Hub) access  
[https://cli.github.com/manual/](https://cli.github.com/manual/). 
- Run `gh auth login`


### Install NVM  

[Install NVM](https://github.com/nvm-sh/nvm#installing-and-updating) by running this:

```bash
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash
```

Then, run this:

```bash
$ source ~/.nvm/nvm.sh
```

Get list of versions:
```bash
$ nvm list-remote
```

Install the version you want:
```bash
$ nvm install 18
$ nvm use 18
```

Or just install latest version:
```bash
$ nvm install stable
```




### Set Ruby Version  
rbenv was installed in step 3, now set the version. 
Via: <https://gorails.com/setup/osx/12-monterey>.  

```
# Add rbenv to bash so that it loads every time you open a terminal
$ echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
$ source ~/.zshrc

# Install Ruby
$ rbenv install 3.0.2
$ rbenv global 3.0.2
$ ruby -v
```

<!--

### 6. Install Jekyll  
Via <https://jekyllrb.com/docs/installation/macos/>

```
$ gem install --user-install bundler jekyll
```

and then get your Ruby version using

```
$ ruby -v
```
Then append your path file with the following, replacing the X.X with the first two digits of your Ruby version.

```
# For Bash
$ echo 'export PATH="$HOME/.gem/ruby/X.X.0/bin:$PATH"' >> ~/.bash_profile
$ source ~/.bash_profile

# For ZSH
$ echo 'export PATH="$HOME/.gem/ruby/X.X.0/bin:$PATH"' >> ~/.zshrc
$ source ~/.zshrc
```

To check that your gem paths point to your home directory run:

```
gem env
```

And check that GEM PATHS: points to a path in your home directory.

-->



### Install Oh My ZSH 

Install Oh My ZSH! via curl

```
$ sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

#### Install Powerline fonts

> Note: many themes require installing the Powerline Fonts in order to render properly.

Clone powerline fonts repo:

```
$ git clone https://github.com/powerline/fonts.git --depth=1
```

Install them:

```
$ cd fonts
$ ./install.sh
```

Delete

```
$ cd ..
$ rm -rf fonts
```

Update plugins and theme

```
$ vi ~/.zshrc
```
```
plugins=(
  git
  bundler
  dotenv
  macos
  rake
  rbenv
  ruby
)

ZSH_THEME="agnoster"
```



## Use it yourself
Fork this repo, or just copy-paste things you need, and make it your own.



## Works on my machine
Works for me, may not work for you.

![Dassit](https://i.giphy.com/media/rjjbSS3k4DIgE/giphy.webp)
