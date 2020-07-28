# New-Mac-Checklist

A checklist I follow when setting up a new Mac's development environment.


## Checklist

### 1. Prep OS X  
- Update OS
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

### 4. Install NVM  

Install NVM by running this:

```bash
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

Then, run this:

```bash
$ source ~/.nvm/nvm.sh
```

### 5. Set Ruby Version  
rbenv was installed in step 3, now set the version. 
Via: <https://gorails.com/setup/osx/10.11-el-capitan>.  
- Install Ruby `rbenv install 2.3.1`
- Make it the global version `rbenv global 2.3.1`  
- Check version `ruby -v`



### 6. Install Jekyll  
- Run `gem install jekyll bundler`



## Use it yourself
Fork this repo, or just copy-paste things you need, and make it your own.



## Works on my machine
Works for me, may not work for you.

![Dassit](http://az616578.vo.msecnd.net/files/2015/09/19/635782305346788765-336606072_2905279.jpg)
