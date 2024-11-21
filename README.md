# ds18b20-2024

This project captures some of the changes to the Raspberry Pi environment that obviates some of the advice that made sense with earlier versions.

The stock Pi OS as of Nov, 2024, performs a lot of the boilerplate setup from the code.  For example, there ia no need to perfrom modprobe operations.

After installation of your Pi OS
- sudo raspi-config
- scroll to interfaces and active 1-Wire

Reboot to capture this change.

Setup your preferred  environment tools.  I use oh-my-zsh with zsh and
asdf for tool version management.

Once you have your python tools installed, create a fold, and virtual environment.
Once in your development folder, if you are using asdf, set the global version of python.
E.g.:

asdf local python 3.13.0t

The code to monitor our temperature tries to read from a dotfile to get its operating values.  If that fails, it defaults to some reasonable defaults in the code.
The dotfile handling capabilities are imported from the dotenv package.

The code to perform the periodic polling of one or more 
