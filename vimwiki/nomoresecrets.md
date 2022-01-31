
= No More Secrets =
-------------------

This project provides a command line tool called `nms`
that recreates the famous data decryption effect seen on screen in
the 1992 hacker movie Sneakers.
For reference,
you can see this effect at 0:35 in
[this movie clip](https://www.youtube.com/watch?v=F5bAa6gFvLs&t=35).
This command works on piped data.
Pipe any ASCII or UTF-8 text to `nms`
and it will apply the Hollywood effect,
initially showing encrypted data,
then starting a decryption sequence
to reveal the original plain-text characters.

Also included
in this project is a program called `sneakers` 
that recreates what we see in the above movie clip.
Note that this program requires
the user to select one of the menu options before it terminates.

By default,
this project has no dependencies, but it does rely on ANSI/VT100
terminal escape sequences to recreate the effect.
Most modern terminal programs support these sequences
so this should not be an issue for most users.

## Table of Contents ##

# [[#download-and-install|Download and Install]]
# [[#usage|Usage]]
# [[#the-nms-library|The NMS Library]]

## Download and Install ##

installing from source by following the instructions below.
-----------------------------------------------------------

To install this project from source
you will need to have the tools `git`
`gcc`, `make`to download and build it.
Install them from your package
manager if they are not already installed.

Once you have the necessary tools installed,
follow these instructions:

##== Install: ====

 git clone https://github.com/bartobri/no-more-secrets.git
 cd ./no-more-secrets
 make nms
 make sneakers   
 sudo make install
##== Uninstall: ====

$ sudo make uninstall

## Usage ==

`nms` on piped data.
Pipe any UTF-8 characters to it and enjoy the magic.
In the below examples, I use a simple directory listing.
```
$ ls -l | nms
$ ls -l | nms -a           // Set auto-decrypt flag
$ ls -l | nms -s           // Set flag to mask space characters
$ ls -l | nms -f green     // Set foreground color to green
$ ls -l | nms -c           // Clear screen
$ nms -v                   // Display version`/pre>
```
####Note
that by default,
after the initial encrypted characters are displayed,
`nms` wait for the user to press a key
before initiating the decryption sequence.
This is how the it is depicted in the movie.

##== Command Line Options ====

`-a`

Set the auto-decrypt flag.
This will automatically start the decryption sequence
without requiring a key press.

`-s`

Set a flag to mask space characters.
This will only mask single blank space characters.
Other space characters such as tabs and newlines will not be masked.

`-f`

Set the foreground color
of the decrypted text to the color specified.
Valid options are white, yellow, black, magenta, blue, green, & red.
This is blue by default.

`-c`

Clear the screen prior to printing any output.
it saves the state of the terminal , and restores it
once the effect is completed.
Note that when using this option,
`nms` requires
the user to press a key before restoring the terminal.

`-v`

Display version info.

## The NMS Library ==

For those who would like to use this effect in their own projects
I have created a C library
that provides simple interface and can easily be used
for any program that runs from the command line.

See [https://github.com/bartobri/libnms LibNMS] for more info.

