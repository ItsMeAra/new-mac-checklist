# New-Mac-Checklist

A checklist I follow when setting up a new Mac's development environment.


## Checklist

### 1. Prep OS X  
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

Show hidden files
- Run `defaults write com.apple.finder AppleShowAllFiles YES`
- Relaunch finder.



### 2. Secure Git(Hub) access  
- [Generate new SSH key](https://help.github.com/articles/generating-ssh-keys/)
- [Generate an access token](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) for Terminal to auth your GitHub account when 2FA is enabled.




### 3. Setup dotfiles  
See [my dotfiles](https://github.com/ItsMeAra/dotfiles) 

During this process, you will setup your dotfiles as well as install [non Mac App Store apps](https://github.com/ItsMeAra/dotfiles/blob/master/brew-cask.txt) all via Homebrew. `#magic`



### 4. Install NVM  

Install NVM by running this:

```bash
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
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
$ nvm install v15.4.0
```





### 5. Set Ruby Version  
rbenv was installed in step 3, now set the version. 
Via: <https://gorails.com/setup/osx/10.15-catalina>.  

```
# Add rbenv to bash so that it loads every time you open a terminal
# For Bash
$ echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
$ source ~/.bash_profile

# For ZSH
$ echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
$ source ~/.zshrc

# Install Ruby, set global default, and check version to confirm
$ rbenv install 3.0.2
$ rbenv global 3.0.2
$ ruby -v
```



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


### 7. Install Oh My ZSH 

Install Oh My ZSH! via curl

```
$ sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

#### Install Powerline fonts

Clone powerline fonts repo:

```
git clone https://github.com/powerline/fonts.git --depth=1
```

Install them:

```
cd fonts
./install.sh
```

Delete

```
cd ..
rm -rf fonts
```

Update plugins and theme

```
vi ~/.zshrc
```
```
plugins=(
  git
  bundler
  dotenv
  osx
  rake
  rbenv
  ruby
)

ZSH_THEME="agnoster"
```
Note: many themes require installing the Powerline Fonts in order to render properly.


## Use it yourself
Fork this repo, or just copy-paste things you need, and make it your own.



## Works on my machine
Works for me, may not work for you.

![Dassit](http://az616578.vo.msecnd.net/files/2015/09/19/635782305346788765-336606072_2905279.jpg)
