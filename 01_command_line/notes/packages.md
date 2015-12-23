## Package management 2m

  (Move to start?)

  e.g. install cheat
  e.g. install PostgreSQL 9.3

  brew install ...
  install home brew
  find app
  install app
  boot config
  taps/custom
  xcode-select -p
  xcode-select --install
  remove app
  ruby/prog lang env

  http://coolestguidesontheplanet.com/installing-homebrew-os-x-yosemite-10-10-package-manager-unix-apps/
  
## Examples
  install homebrew
  search/install
  remove
  install cask
  search/install

## Package management 2m

  https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/Installation.md

  Get Xcode
  Get Xcode 6.3 .
  xcode 6.1 for yosemite
  Download and install it, you also need to open Xcode agree to the license and it will install its components.

  yosemite-xcode-install
  Get Command Line Tools

  xcode-select --install

  Install Homebrew

  To download install Homebrew run the install script on the command line as below and let the script do its thing:

  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

  homebrew-osx-install-mountain-lion

  Download and install Xquartz brew will moan if it is not installed.

  After installing and as suggested in the command line, to check for any issues with the install run:

  brew doctor

  To search for an application:

  brew search

  To install

  brew install <application-name>

  To list all apps installed by Homebrew

  brew list

  To remove an installed application

  brew remove <application-name>

  To update Homebrew

  brew update

  To see what else you can do

  man brew

  Where does Homebrew install stuff …. in the Cellar

  /usr/local/Cellar/


  Skip to content
  This repository

      Pull requests
      Issues
      Gist

      @kmcd
  183
  7,871

      2,862

  caskroom/homebrew-cask

  homebrew-cask/USAGE.md
  4caa121 21 days ago
  @vitorgalvao vitorgalvao usage: add '$' to completion commands
  14 contributors
  @rolandwalker
  @vitorgalvao
  @phinze
  @adamchainz
  @tpitale
  @voanhduy1512
  @ujovlado
  @leoj3n
  @jedahan
  @xyb
  @hanjianwei
  @linc01n
  @Cottser
  @pasku
  242 lines (167 sloc) 9.2 KB
  How to Use Homebrew-cask
  Getting Started

  First ensure you have Homebrew version 0.9.5 or higher:

  $ brew --version
  0.9.5

  Install the homebrew-cask tool:

  $ brew install caskroom/cask/brew-cask

  Frequently Used Commands

  Homebrew-cask is implemented as a subcommand of Homebrew. All homebrew-cask commands begin with brew cask. Homebrew-cask has its own set of command verbs many of which are similar to Homebrew’s. The most frequently-used commands are:

      search — searches all known Casks
      install — installs the given Cask
      uninstall — uninstalls the given Cask

  Searching for Casks

  The brew cask search command accepts a series of substring arguments, and returns tokens representing matching Casks. Let’s see if there’s a Cask for Google Chrome:

  $ brew cask search chrome
  google-chrome

  A search command with no search term will list all available Casks:

  $ brew cask search
  # <list of all available Casks>

  Installing Casks

  The command brew cask install accepts a Cask token as returned by brew cask search. Let’s try to install Google Chrome:

  $ brew cask install google-chrome
  ==> Downloading https://dl.google.com/chrome/mac/stable/GGRO/googlechrome.dmg
  ==> Success! google-chrome installed to /opt/homebrew-cask/Caskroom/google-chrome/stable-channel
  ==> Linking Google Chrome.app to /Users/paulh/Applications/Google Chrome.app

  Uninstalling Casks

  Easy peasy:

  $ brew cask uninstall google-chrome

  This will both uninstall the Cask and remove symlinks which were created in ~/Applications.

  To uninstall all versions of a Cask, use --force:

  $ brew cask uninstall --force google-chrome

  Note that uninstall --force is currently imperfect. See the man page for more information.
  Other Commands

      info — displays information about the given Cask
      list — with no args, lists installed Casks; given installed Casks, lists staged files
      fetch — downloads Cask resources to local cache (with --force, re-download even if already cached)
      doctor — checks for configuration issues
      cleanup — cleans up cached downloads (with --outdated, only cleans old downloads)
      home — opens the homepage of the given Cask; or with no arguments, the homebrew-cask project page
      update — a synonym for brew update
      zap — try to remove all files associated with a Cask (including resources which may be shared with other applications)

  The following commands are for Cask authors:

      audit — verifies installability of Casks
      cat — dumps the given Cask to the standard output
      create — creates a Cask and opens it in an editor
      edit — edits the given Cask

  The following aliases and abbreviations are provided for convenience:

      ls — list
      -S — search
      rm, remove — uninstall
      up — update
      dr — doctor

  Tab Completion

  Homebrew/homebrew-completions supports bash and fish completions (only for brew-cask right now). Install them with:

  $ brew install homebrew/completions/brew-cask-completion

  For zsh completion support, simply run:

  $ brew install `zsh-completions`

  Inspecting Installed Casks

  List all installed Casks

  $ brew cask list
  adium          google-chrome     onepassword

  Show details about a specific Cask:

  $ brew cask info caffeine
  caffeine: 1.1.1
  http://lightheadsw.com/caffeine/
  Not installed
  https://github.com/caskroom/homebrew-cask/blob/master/Casks/caffeine.rb

  Updating/Upgrading Casks

  Since the homebrew-cask repository is a Homebrew Tap, you’ll pull down the latest Casks every time you issue the regular Homebrew command brew update. Currently, homebrew-cask cannot always detect if an Application has been updated. You can force an update via the command brew cask install --force. We are working on improving this.

  It is generally safe to run updates from within an Application.
  Updating/Upgrading the Homebrew-cask Tool

  When a new version homebrew-cask is released, it will appear in the output of brew outdated after running brew update. You can upgrade it via the normal Homebrew brew upgrade workflow:

  $ brew update && brew upgrade brew-cask && brew cleanup && brew cask cleanup

  Additional Taps (optional)

  The primary homebrew-cask Tap includes most of the Casks that a typical user will be interested in. There are a few additional Taps where we store different kinds of Casks.
  Tap name 	description
  caskroom/versions 	contains alternate versions of Casks (e.g. betas, nightly releases, old versions)
  caskroom/fonts 	contains Casks that install fonts, which are kept separate so we can educate users about the different licensing landscape around font installation/usage
  caskroom/unofficial 	contains Casks that install unofficial builds or forks

  There are also alternate Cask Taps maintained by users.

  You can tap any of the above with a brew tap command:

  $ brew tap <tap_name>

  after which, Casks from the new Tap will be available to search or install just like Casks from the main Tap. brew update will automatically keep your new Tap up to date.

  You may also specify a fully-qualified Cask token (which includes the Tap) for any brew cask command. This will implicitly add the Tap if you have not previously added it with brew tap:

  $ brew cask install caskroom/fonts/font-symbola

  Options

  brew cask accepts a number of options:

      --version: print version and exit
      --debug: output debug information
      --no-binaries: skip symlinking executable binaries into /usr/local/bin

  You can also modify the default installation locations used when issuing brew cask install:

      --caskroom=/my/path determines where the actual applications will be located. Should be handled with care — setting it outside /opt or your home directory might mess up your system. Default is /opt/homebrew-cask/Caskroom.
      --appdir=/my/path changes the path where the symlinks to the applications (above) will be generated. This is commonly used to create the links in the root Applications directory instead of the home Applications directory by specifying --appdir=/Applications. Default is ~/Applications.
      --prefpanedir=/my/path changes the path for PreferencePane symlinks. Default is ~/Library/PreferencePanes
      --qlplugindir=/my/path changes the path for Quicklook Plugin symlinks. Default is ~/Library/QuickLook
      --fontdir=/my/path changes the path for Fonts symlinks. Default is ~/Library/Fonts
      --binarydir=/my/path changes the path for binary symlinks. Default is /usr/local/bin
      --input_methoddir=/my/path changes the path for Input Methods symlinks. Default is ~/Library/Input Methods
      --screen_saverdir=/my/path changes the path for Screen Saver symlinks. Default is ~/Library/Screen Savers

  To make these settings persistent, you might want to add the following line to your .bash_profile or .zshenv:

  # Specify your defaults in this environment variable
  export HOMEBREW_CASK_OPTS="--appdir=/Applications --caskroom=/etc/Caskroom"

  Note that you still can override the environment variable HOMEBREW_CASK_OPTS by explicitly providing options in the command line:

  # Will force the Chrome app to be linked to ~/Applications
  # even though HOMEBREW_CASK_OPTS specified /Applications
  $ brew cask install --appdir="~/Applications" google-chrome

  Advanced searching

  The default search algorithm is a lax substring approach, which does not use the command-line arguments exactly as given. If you need to specify a search more precisely, a single search argument enclosed in / characters will be taken as a Ruby regular expression:

  $ brew cask search '/^google.c[a-z]rome$/'
  google-chrome

  Other Ways to Specify a Cask

  Most brew cask commands can accept a Cask token as an argument. As described above, the token on the command line can take the form of:

      A token as returned by brew cask search, eg: google-chrome.
      A fully-qualified token which includes the Tap, eg: caskroom/fonts/font-symbola.

  brew cask also accepts three other forms as arguments

      A path to a Cask file, eg: /usr/local/Cellar/brew-cask/0.25.0/Casks/google-chrome.rb.
      A curl-retrievable URI to a Cask file, eg: https://raw.github.com/caskroom/homebrew-cask/f54bbfaae0f2fa7210484f46313a459cb8a14d2f/Casks/google-chrome.rb.
      A file in the current working directory, eg: my-modfied-google-chrome.rb. Note that matching Tapped Cask tokens will be preferred over this form when there is a conflict. To force the use of a Cask file in the current directory, specify a pathname with slashes, eg: ./google-chrome.rb.

  The last three forms are intended for users who wish to maintain private Casks.
  Taps

  You can add Casks to your existing (or new) Taps: just create a directory named Casks inside your Tap, put your Cask files there, and everything will just work.

    Status API Training Shop Blog About Pricing

    © 2015 GitHub, Inc. Terms Privacy Security Contact Help


  brew cask search font | sed '/Partial/d' | xargs brew cask info | grep http | xargs open



### VO 300w
  https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/Installation.md

  Get Xcode
  Get Xcode 6.3 .
  xcode 6.1 for yosemite
  Download and install it, you also need to open Xcode agree to the license and it will install its components.

  yosemite-xcode-install
  Get Command Line Tools

  xcode-select --install


  Install Homebrew

  To download install Homebrew run the install script on the command line as below and let the script do its thing:

  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

  Download and install Xquartz brew will moan if it is not installed.

  After installing and as suggested in the command line, to check for any issues with the install run:

  brew doctor

  To search for an application:

  brew search

  To install

  brew install <application-name>

  To list all apps installed by Homebrew

  brew list

  To remove an installed application

  brew remove <application-name>

  To update Homebrew

  brew update

  To see what else you can do

  man brew

  Where does Homebrew install stuff …. in the Cellar

  caskroom/homebrew-cask

  Homebrew-cask is implemented as a subcommand of Homebrew. All

  homebrew-cask commands begin with brew cask. Homebrew-cask has its own set of command verbs many of which are similar to Homebrew’s. The most frequently-used commands are:

      search — searches all known Casks
      install — installs the given Cask
      uninstall — uninstalls the given Cask

  Searching for Casks

  $ brew cask search chrome
  google-chrome

  A search command with no search term will list all available Casks:

  $ brew cask search
  # <list of all available Casks>

  Installing Casks

  The command brew cask install accepts a Cask token as returned by brew cask search. Let’s try to install Google Chrome:

  $ brew cask install google-chrome
  $ brew cask uninstall google-chrome

  This will both uninstall the Cask and remove symlinks which were created in ~/Applications.

  To uninstall all versions of a Cask, use --force:

  $ brew cask uninstall --force google-chrome

  Note that uninstall --force is currently imperfect. See the man page for more information.

  Other Commands

  info — displays information about the given Cask
  list — with no args, lists installed Casks; given installed Casks, lists staged files
  fetch — downloads Cask resources to local cache (with --force, re-download even if already cached)
  doctor — checks for configuration issues
  cleanup — cleans up cached downloads (with --outdated, only cleans old downloads)
  home — opens the homepage of the given Cask; or with no arguments, the homebrew-cask project page
  update — a synonym for brew update
  zap — try to remove all files associated with a Cask (including resources which may be shared with other applications)

  Tab Completion

  Homebrew/homebrew-completions supports bash and fish completions (only for brew-cask right now). Install them with:

  $ brew install homebrew/completions/brew-cask-completion

  List all installed Casks

  $ brew cask list
  adium          google-chrome     onepassword

  Show details about a specific Cask:

  $ brew cask info caffeine
  caffeine: 1.1.1
  http://lightheadsw.com/caffeine/
  Not installed
  https://github.com/caskroom/homebrew-cask/blob/master/Casks/caffeine.rb

  Updating/Upgrading Casks

  Since the homebrew-cask repository is a Homebrew Tap, you’ll pull down the latest Casks every time you issue the regular Homebrew command brew update.

  When a new version homebrew-cask is released, it will appear in the output of brew outdated after running brew update. You can upgrade it via the normal Homebrew brew upgrade workflow:

  $ brew update && brew upgrade brew-cask && brew cleanup && brew cask cleanup

  Additional Taps (optional)

  The primary homebrew-cask Tap includes most of the Casks that a typical user will be interested in. There are a few additional Taps where we store different kinds of Casks.

  Tap name 	description
  caskroom/versions 	contains alternate versions of Casks (e.g. betas, nightly releases, old versions)

  caskroom/fonts 	contains Casks that install fonts, which are kept separate so we can educate users about the different licensing landscape around font installation/usage

  caskroom/unofficial 	contains Casks that install unofficial builds or forks

  $ brew tap <tap_name>

  after which, Casks from the new Tap will be available to search or install just like Casks from the main Tap. brew update will automatically keep your new Tap up to date.

  You may also specify a fully-qualified Cask token (which includes the Tap) for any brew cask command. This will implicitly add the Tap if you have not previously added it with brew tap:

  $ brew cask install caskroom/fonts/font-symbola

  Options

  brew cask accepts a number of options:

      --version: print version and exit
      --debug: output debug information
      --no-binaries: skip symlinking executable binaries into /usr/local/bin

  Advanced searching

  $ brew cask search '/^google.c[a-z]rome$/'
  google-chrome

  brew cask search font | sed '/Partial/d' | xargs brew cask info | grep http | xargs open

## OUTRO 1m

