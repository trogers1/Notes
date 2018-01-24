# Linting with the Command Line #

Using linting programs via the command line is fairly easy. It works well to have all of the errors in one terminal screen and work with `vim` in another. So far, `pylint` seems very thorough. `flake8` is also good.

The process was made more difficult by the fact that I use virtualenv, so I started by [adding virtualenv bin folder to my $PATH](https://github.com/AtomLinter/linter-flake8/issues/132)(The anwswer from Nov 21, 2017).

Then, I started by virtualenv and installed with `python -m pip install <whatever>` the linters. They should now be in the bin folder.

To add something to the path, simply open the `.bash_profile` file in the `$HOME` directory. I went to the bottom and added two commands:

```.bash_profile
#Set the path:
PATH="/This/is/A/Path/To/A/VirtualEnv/bin:${PATH}"
#export it
export PATH
```

After that, you should be able to use them in the command line. 
