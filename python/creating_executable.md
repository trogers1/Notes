# Creating a Windows/Unix Executable from Python Scripts #

Some useful references:
* [With wine](https://andreafortuna.org/technology/how-to-cross-compile-a-python-script-into-a-windows-executable-on-linux/)
* [With wine and winetricks](http://sparkandshine.net/en/build-a-windows-executable-from-python-scripts-on-linux/)
* [Wine documentation](https://wiki.winehq.org/Wine_User%27s_Guide)
* [PyInstaller Documentation](https://pyinstaller.readthedocs.io/en/stable/)
* [PyInstaller Tutorial -- Medium](https://medium.com/dreamcatcher-its-blog/making-an-stand-alone-executable-from-a-python-script-using-pyinstaller-d1df9170e263)
* [StackOverflow PyInstaller Example](https://stackoverflow.com/questions/2950971/cross-compiling-a-python-script-on-linux-into-a-windows-executable)

## Same-Platform Executable Creation ##

This is relatively simple, as PyInstaller can create standalone executables for whatever platform it is being run on of the major three (Windows, MacOS, and Linux) without too much fuss. 

First, install PyInstaller using `pip`. You may want to do this within the virtual environment that you are building your application in if you don't want to contaminate your global version of Python.
`python -m pip install pyinstaller`

__Note__: If using windows, [PyWin32](https://sourceforge.net/projects/pywin32/files/) will need installed as well.

After installing PyInstaller, it's probably a good idea to test your script one more time. Then, if satisfied, use PyInstaller to compile your script. If you want one file, do so with the `--onefile` flag. Otherwise, libraries will be distributed as separate files along with the executable.
`pyinstaller --onefile <scriptname>.py`

Your executable can then be found in the _dist_ directory in the folder containing your scripts.

Now you should be done!

A note from the Medium article above: 
```text
If your python script depends on additional executables say for example, phantomjs or chromedriver. You may have to put these executable in the same directory of your executable!

For these type of dependencies, when I’m working on Windows Platform. I usually package them using NSIS.
```


## Windows Executable from Unix Platform ##

~~Firstly, use `homebrew`, or `apt-get`, or some sort of package manager to install `wine`.~~

~~MacOS with homebrew:~~
~~`$ brew install wine`~~

~~Linux with apt-get:~~
~~`sudo apt-get install wine`~~

~~Then you need to get the appropriate Windows MSI for the Python distribution that you want. You can get that at the [Python website](https://www.python.org/download/releases/3.0/)~~

Yeah. I don't know how to do this yet. I tried getting wine to run python3, install python3 various ways, etc. Couldn't get it to work...


