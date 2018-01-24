# Linting with Atom #

I have found the text editor [Atom](www.atom.io) to be my preferred linter if using a GUI program. So far, a combination of `Pylint` and `pycodestyle` have been working fairly well, however I have not been able to get `flake8` to work as of yet.

The process was made more difficult by the fact that I use virtualenv, so I started by [adding virtualenv bin folder to my $PATH](https://github.com/AtomLinter/linter-flake8/issues/132)(The anwswer from Nov 21, 2017).

Then, I started by virtualenv and installed with `python -m pip install <whatever>` the linters. They should now be in the bin folder.

To add something to the path, simply open the `.bash_profile` file in the `$HOME` directory. I went to the bottom and added two commands:

```.bash_profile
#Set the path:
PATH="/This/is/A/Path/To/A/VirtualEnv/bin:${PATH}"
#export it
export PATH
```

After that, you should be able to use them in the command line as a bonus. Now, they should be working.
