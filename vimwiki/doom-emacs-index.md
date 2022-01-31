
[installing packages](installing-packages)

[bin doom utility](bin/doom-utility)

[Doom cheatsheet#1](Doom-cheatsheet1#1)

[Doomcheatsheet2](Doomcheatsheet2)

[Doom-tips](Doom-tips)

[Doom workflow](Doom-workflow)

[org basics dt](org-basics-dt)

[org note taking](org.-note-taking)

(require 'whitespace)
(setq whitespace-line-column 80) ;; limit line length
(setq whitespace-style '(face lines-tail))

(add-hook 'prog-mode-hook 'whitespace-mode)

The above snippet will enable whitespace-mode only in major modes
for programming. If you want to enable whitespace-mode everywhere
you might want to do this instead:

(global-whitespace-mode +1)

to save and quit
----------------
`:w` and `:q`

to split the screen into two side-by-side windows,
--------------------------------------------------
`SPC w v`.

To navigate to other files within the same project
--------------------------------------------------
`SPC SPC`

If you want to open a file from a different project,
----------------------------------------------------
`SPC p p`

to switch between files that you have already opened
----------------------------------------------------
`SPC ,`

To close the currently selected window:
---------------------------------------
`SPC w c`

To open the Neotree view:
-------------------------
`<f8>`

If you are currently in the neotree window and you want to close it,
you can just press the `Escape key` or the `q` key.
`SPC w c` will still work,
but escape is a lot more intuitive to me
since I feel like I am closing out a temporary dialog.


Conclusion
----------
One final tip 
If you decide that you don’t actually want to call a function
after all, you can always press `Ctrl-G`
to cancel whatever you were in the middle of doing.
