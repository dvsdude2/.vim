Installing packages
-------------------

Type `M-x list-packages` to open the package list.
Press ‘i’ to mark for installation, 
‘u’ to unmark, and ‘x’ to perform the installation.
Press ‘RET’ to read more about installing and using each package.

If you don’t see the package listed there,
you may need to add another package source
to your package-archives variable.
See the section on adding a package source.

You may want to start by installing the paradox package.
This will allow you to use the command paradox-list-packages,
which among other things gives the ability to sort package list
by GitHub popularity. Starting with the most popular packages is
a good way to find the most useful and effective ones.

If you move to a different system and you would like to quickly 
install all of your previously installed packages,
look into ‘M-x package-install-selected-packages’.
If you use UsePackage, the :ensure t property will
ll Emacs to install a package if it hasn’t already been installed.
