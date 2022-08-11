# The Most Common Error with M1 Mac Homebrew

If you're someone like me who has the new Macbook Air with the M1 chip, you're likely to encounter this error if you use Homebrew's `brew` command:
```
Error: Cannot install in Homebrew on ARM processor in Intel default prefix (/usr/local)!
Please create a new installation in /opt/homebrew using one of the
"Alternative Installs" from:
  https://docs.brew.sh/Installation
You can migrate your previously installed formula list with:
  brew bundle dump
```
This error is likely due to one or more of the following reasons:
- You incorrectly followed the installation steps for Homebrew.
- You have Homebrew installed in the wrong directory.
- You have Homebrew installed in the right directory, yet you did not use the `brew update` command.


### Installation
[Homebrew Documentation] doesn't mention this, but you should always enter the `/opt/homebrew` directory whenever installing Homebrew or using any `brew` commands.
Follow these commands for installation:
1) Open your terminal and enter the /opt directory using the command `cd /opt`.
2) Make a directory called 'homebrew' using the command `mkdir homebrew` and enter the directory using `cd homebrew`.
3) Use the command `curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew` to install Homebrew.
4) Enter the command `eval "$(homebrew/bin/brew shellenv)"`.
5) Enter the command `brew update --force --quiet`.
6) Enter the command `chmod -R go-w "$(brew --prefix)/share/zsh"`.

### Troubleshooting
 - If you installed Homebrew in the wrong directory, reinstall Homebrew in the correct directory using the installation steps above. 
 - If you have installed Homebrew in the correct directory, simply enter the `/opt/homebrew` directory using `cd /opt/homebrew` and run the command `brew update`.
 

By following the installation and troubleshooting steps, it should get rid of the error. A common practice is to always update software before use because it can usually solve several errors, so continue to use `brew update` as your first troubleshooting option for Homebrew if you have already installed it correctly.





[Homebrew Documentation]: <https://docs.brew.sh/Installation>

 
