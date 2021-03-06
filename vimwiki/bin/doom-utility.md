
The bin/doom utility
This utility is your new best friend.
It won’t spot you a beer,
but it’ll shoulder much of the work associated
with managing and maintaining your Doom Emacs configuration.
Not least of which is installation of
and updating Doom and your installed packages.

It exposes a variety of commands.
`bin/doom help` will list them all,
but here is a summary of the most important ones:

`doom sync`:
This synchronizes your config with Doom Emacs.
It ensures that needed packages are installed,
orphaned packages are removed
and necessary metadata correctly generated.
Run this whenever you modify your doom! block or packages.el file.
You’ll need doom sync -u
if you override the recipe of package installed by another module.

`doom upgrade`:
Updates Doom Emacs (if available) and all its packages.

`doom env`:
(Re)generates an “envvar file”,
which is a snapshot of your shell environment
that Doom loads at startup.
If your app launcher or OS launches Emacs
in the wrong environment you will need this.
**This is required for GUI Emacs users on MacOS.**

`doom doctor`:
If Doom misbehaves,
the doc will diagnose common issues with your
installation, system and environment.

`doom purge`:
Over time, the repositories for Doom’s plugins will accumulate.
Run this command from time to time to delete old, orphaned packages
and with the -g switch to compact existing package repos.

Use `doom help`
to see an overview of the available commands that doom provides
doom help COMMAND to display documentation for a particular COMMAND.

I recommend you add ~/.emacs.d/bin to your PATH
so you can call doom directly and from anywhere.
Accomplish this by adding this to your .bashrc or .zshrc file:
`export PATH=”$HOME/.emacs.d/bin:$PATH”`

