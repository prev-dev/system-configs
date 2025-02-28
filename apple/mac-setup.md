# Basic setup for new Mac dev machines

## Finder Preferences
````shell
# show path bar
defaults write com.apple.finder ShowPathbar -bool true

# show hidden files
defaults write com.apple.finder AppleShowAllFiles YES

# show status bar
defaults write com.apple.finder ShowStatusBar -bool true

# show Library folder
chflags nohidden ~/Library

killall Finder;
````
## xcode and tool chain
````shell
xcode-select --install
````
## homebrew
This will install [Homebrew](https://brew.sh/), a package manager for MacOS 
that is used to install various opensource tools. Normal caveats about running scripts
directly from the Internet apply, please read and verify first.

The curl options are -f for fail silently, s for silent mode, S for show errors
and L for follow redirects
````
# Check the script first 
curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh | less

# Download it
curl -o homebrew-install.sh https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh

# Run it
/bin/bash homebrew-install.sh

# Follow the provided steps to enable brew in your path, then run this to disable analytics
brew analytics off
````
## install some packages with brew
````
brew install \
htop
