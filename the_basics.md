# Setting up the basics on OS X

If you have not installed the basics yet, here is a guide to set yourself up for success.
This guide will be focussing on zsh, as this is now the default shell that ships with OS X.


## First things first: xcode
In order to set your machine up for python development, you will need to have xcode installed.

Start by pressing the `command` and `spacebar` keys simultaneously to open spotlight search,
type `terminal` in the window and press `enter`.
In the new terminal window, type the following:
```zsh
xcode-select -p
```
If you receive the following output, then Xcode is installed:

```output
/Library/Developer/CommandLineTools
```

If you received an error, then in your web browser install Xcode from the App Store and accept the default options.

Once Xcode is installed, return to your Terminal window. 
Next, you’ll need to install Xcode’s separate Command Line Tools app, which you can do by typing:
```zsh
xcode-select --install
```
At this point, Xcode and its Command Line Tools app are fully installed, 
and we are ready to install the package manager Homebrew.


## Installing Homebrew: brew
To install Homebrew, type this into your Terminal window:
```zsh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
Once the installation process is complete, we’ll put the Homebrew directory at the top of the `PATH` environment variable. 
This will ensure that Homebrew installations will be called over the tools that 
Mac OS X may select automatically that could run counter to the development environment we’re creating.

```zsh
echo 'if ! [[ :$PATH: == *:"/usr/local/bin":* ]] ; then export PATH=/usr/local/bin:$PATH ; fi' >> ~/.zprofile
```

To make sure that everything went smoothly (or if you ever need to troubleshoot things in the future) run:
```zsh
brew doctor
```
Follow the instructions (if any) from that output.  If everything is set up perfectly there will be no action points suggested by homebrew.


## Install a few important things with homebrew (brew)

#### Install the newest version of zsh
to get all the shiny new things
```zsh
brew install zsh
```

#### Install a non-system version of python3
to ensure we don't mess up our whole system later on
```zsh
brew install python3
```
If everything went according to plan, running `which python3` should yield `/usr/local/bin/python3`

#### Install a few miscellaneous things that will come in handy:
```zsh
brew install git htop openssl readline sqlite3 xz zlib
```

#### Install pyenv
a tool for simple Python version management (i.e. 3.6.10, 3.7.6, 3.8.1, etc)
```zsh
brew install pyenv
```

#### Install pipx
a tool to help you install and run end-user applications written in Python
```zsh
brew install pipx
pipx ensurepath
```


## Install another few things with pipx
#### Install pipenv
the official Python-recommended resource for managing package dependencies.
```zsh
pipx install pipenv
```

#### Install pipenv bolt-on functions
pipenv-pipes helps you to activate pipenv environments, automatically change to the environment working directory.
From anywhere, simply type `pipes` to see your environments, select one and enter.
pipenv-setup helps you to keep your environment and your `setup.py` file in sync via `pipenv-setup sync`
```zsh
pipx install pipenv-pipes
pipx install pipenv-setup
```

## Done!
If you followed all the steps up to here, you've done well! Give yourself a pat on the back.