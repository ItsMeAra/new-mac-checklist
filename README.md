# New-Mac-Checklist

A checklist I follow when setting up a new Mac's development environment.


## Checklist

### 1. Prep OS X  
- Download and install latest version of Xcode from the Mac App Store. (if needed)
- Install Xcode Command Line Tools by running `xcode-select --install` in terminal.

Show hidden files
- Run `defaults write com.apple.finder AppleShowAllFiles YES`
- Relaunch finder.



### 2. Secure Git(Hub) access  
- [Generate new SSH key](https://help.github.com/articles/generating-ssh-keys/)
- [Generate an access token](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) for Terminal to auth your GitHub account when 2FA is enabled.



### 3. Setup dotfiles  
See [my dotfiles](https://github.com/ItsMeAra/dotfiles) 

During this process, you will setup your dotfiles as well as install [non Mac App Store apps](https://github.com/ItsMeAra/dotfiles/blob/master/brew-cask.txt) all via Homebrew. `#magic`



### 4. Set Ruby Version  
rbenv was installed in step 3, now set the version. 
Via: <https://gorails.com/setup/osx/10.11-el-capitan>.  
- Install Ruby `rbenv install 2.3.1`
- Make it the global version `rbenv global 2.3.1`  
- Check version `ruby -v`



### 5. Install Jekyll & Co  
- Run `gem install bundler sass jekyll rouge`
- ZOMG so easy.



### 6. Download Mac App Store Apps  
- [droplr](https://itunes.apple.com/us/app/droplr/id498672703?mt=12)
- [Transmit](https://itunes.apple.com/us/app/transmit/id403388562?mt=12)
- [Ulysses](https://itunes.apple.com/us/app/ulysses/id623795237?mt=12)
- [Slicy](https://itunes.apple.com/us/app/slicy/id512533449?mt=12)
- Moom



### 7. Setup Atom  
- Enable `atom` Terminal commands: from Atom.app, open the Atom menu and select *Install Shell Commands*
- Install favorite packages
  - [Wrap in tag](https://atom.io/packages/atom-wrap-in-tag)
  - [Selector to tag](https://atom.io/packages/selector-to-tag)
  - [Pigments](https://atom.io/packages/pigments)
  - [Linter](https://atom.io/packages/linter) and [`.scss` linter](https://atom.io/packages/linter-scss-lint)
- Install [Dracula](https://draculatheme.com/atom/) theme
  - Go to Atom -> Preferences...
  - Select the Install tab
  - Click the Themes button to the right of the search box
  - Enter dracula-theme in the search box



## Use it yourself
Fork this repo, or just copy-paste things you need, and make it your own.



## Works on my machine
Works for me, may not work for you.

![Dassit](http://az616578.vo.msecnd.net/files/2015/09/19/635782305346788765-336606072_2905279.jpg)
