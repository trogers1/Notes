# Restarting X session (GNOME 3) #

This covers restarting the GNOME 3 GUI if making changes and not wanted to completely logout/shutdown your computer.

From [this Stack Exchange answer](https://unix.stackexchange.com/a/87195), press `Ctrl` `Alt` and `F3` to start the virtual terminal.

Login at the prompt (entering your system username first).

Then use command`sudo /etc/init.d/gdm3 restart` or `sudo service gdm3 restart`.

Press `Ctrl` `Alt` and `F2` to end the virtual terminal.

NOTE: I have not yet gotten this to work fully. I get get the virtual terminal to work, but restarting and returning to the GUI has not yet worked. It required a shutdown restore.
