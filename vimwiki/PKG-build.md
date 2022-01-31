
#LBRY PKGBUILD (MY SECOND )
-----------------------------------------

###these are the step I took to rebuild unmaintained package

- get a copy of the deb file you wan't
- use debtap app to make pkgbuild file
     Q: How do I use debtap?
     A: The syntax is quite simple actually:
        debtap [options] package_filename For example:
       'debtap world-of-goo-demo_1.0_i386.deb`
    
Available options:
-h  --help        Prints help
-u  --update      Update debtap database
-q  --quiet       Bypass all questions, except for editing metadata file(s)
-Q  --Quiet       Bypass all questions (not recommended)
-s  --pseudo      Create a pseudo-64-bit package from a 32-bit .deb package
-w  --wipeout     Wipeout versions from all dependencies, conflicts etc.
-p  --pkgbuild    Additionally generate a PKGBUILD file
-P  --Pkgbuild    Generate a PKGBUILD file only
-v  --version     Print version

 open term enter debtap -p -q <file-name>
    - the p is for pkgbuid 
    - the q is to not ask questions (you gonna edit it anyways)
    - from what I can tell 'P'will make just the install file.
    - 'p'will make a install file + tar.zsh file.
    - 'w'will make just the tar.zsh file.
- debtap will ask what editor you want to use ....don't  hit enter
- you will edit the file after anyways.debtap will produce two files
- once you close the files it will produce the tar.zsh. 
- I did not see a diff if the file was edited before or after 
- it appears to be the same tar.zsh,could be wrong????
- using the older install file as a template 
- change what is diff. write to file
- open terminal in file dir.and use pacman to install
- use pacman -U <name of tar.zsh>


use debtap app to make pkgbuild file
used old pkgbuild file to fix the new one
change -dependants to:

depends=('desktop-file-utils' 'gconf' 'hicolor-icon-theme' 'libappindicator-gtk2' 'libnotify' 'libxcb' 'libxss' 'libxtst' 'mesa')

and the bttm 6 lines to:

package() {
    install -dm 755 "$pkgdir/usr/bin/"
    tar -xf "$srcdir/data.tar.xz" -C "$pkgdir"
    ln -s "/opt/LBRY/lbry" "$pkgdir/usr/bin/lbry"
    ln -s "/opt/LBRY/resources/static/daemon/lbrynet" "$pkgdir/usr/bin/"
}


'''''''''''''''''''''''''''''''''''''''draft
- get a copy of the deb file you wan't
- open term enter debtap -p -q <file-name>
    - the p is for pkgbuid 
    - the q is to not ask questions (you gonna edit it anyways)
    - from what I can tell 'P'will make just the install file.
    - 'p'will make a install file + tar.zsh file.
    - 'w'will make just the tar.zsh file.
- debtap will ask what editor you want to use ....don't  hit enter
- you will edit the file after anyways.debtap will produce two files
- once you close the files it will produce the tar.zsh. 
- I did not see a diff if the file was edited before or after 
- it appears to be the same tar.zsh,could be wrong????
- using the older install file as a template 
- change what is diff. write to file
- open terminal in file dir.and use pacman to install
- use pacman -U <name of tar.zsh>
