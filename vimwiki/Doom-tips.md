Some tips to learn the keybindings in Doom and Evil
in the process of migrating from my vanilla Emacs settings.

overview of keybindings 
------------------------
`SPC`-`h`-`b`-`b`.

Other good references:

Narra’s Blog - Doom Tips and Howtos
Org Mode Shortcuts for Emacs Doom
Gist of Hjertnes
Evil-mode collection
Doom leader-key is SPC and localleader-key is SPC-m. 
When in Insert mode use M-SPC or M-SPC-m to call the menu available 
as if in the Normal mode. Else change mode with ESC or jk binding. 
To toggle between Emacs state and Evil use C-z.

To show all your keybindings SPC-h b b

Most used keys
--------------
There are keys I mostly need to remember 
and there are also listen in their respective groups below:

Normal mode
-----------
zx kill buffer
SPC-w w move to buffer
zz center line
SPC-i r insert from evil-register or 0p when you know it’s register number 0 
viw select word under cursor or inner word under the cursor
vio select all inner and inclding a symbol
va( selecte all around the bracket ( or any symbol  eg. va"
di( and yi( is both delete and yank inner words respectively.
ciw clear the inner word under the cursor and move to inner mode.
SPC-s s search word or fw and Fw.
SPC-TAB . change workspace.

Insert mode
-----------
C-w kill word bakword
M-d kill word forward

Navigation
----------
When in the Normal mode:

C-b and C-f for page backward and page forward (whole page)
C-u and C-d for half page up and down
z-z move line to center of screen
fw  -find w or any word/symbols in a line.or backward with f
shift-l and shift-h moves cursor to lower (l) or higher (h) screen
shift-m moves cursor to the middle of the screen
split windows with shorcut :sp or window-split c-w s -vsplit c-w v.
sPC-s d search current directory or Spc-s p current project
SPC-' resume last search

Editing
-------
In Normal mode:

db delete backward till next whitespace
d$ delete to end of line from cursor
d0 delete to start of line from cursor
ds( delete columns or any parantheses specify after s ie. symbols
cw kill from cursor position to next whitespace
4cw kill 4 words (or any number) forward
ci{ kill all within the curly bracket when the cursor is inside.
    Other symbols can also be specified and when cursor is inside 
[o and ]o will insert newline above or below respectively
C-j will cut/split the sentence
gU for UPPERCASE or gu lowercase or g~ to toggle between
:e edit file
:w save file
viw select a word under the cursor
* select all word under the cursor in the buffer
# select all word in the same line
/ search word
vio select all inner and inclding a symbol
va( selecte all around the bracket ( or any other symbol
di( and yi( is both delete and yank inner words respectively.
ciw clear the inner word under the cursor and move to inner mode.
Spc-s s search word or fw and Fw
S-" surround the selected word ie. in visual mode, with selected symbol eg. " in this case.
g-S-" surround the selected word with symbol with additional newline
cs"' change the surround or delimiter " to ' symbol
ds" to delete the delimiters "
In Insert mode:

C-w delete word backward
In Visual mode:

Block all line and press = to do indentation

Multiedit
---------
In a file one at a time
Doom uses multiedit package
otherwise it’s like multiple-cursors package plus iedit package.
Basic keybinding is M-d or M-D.
It works both in Normal and Visual mode.

In Normal mode, when the course under a word, pressing M-d will 
select the word, repeating M-d mark forward and M-D mark backward. 
Use C-n and C-p for next and previous selected word.
In Visual mode, when you have made selection pressing R 
will select all the marked section in the whole document.

Press Enter to deselect or reselect the marked section.

All in a file
-------------
Select the text then R

Search and replace in a project
-------------------------------
Search the text with SPC-s p.
When all the files are listed, enter swiper edit with C-c C-e.
Select the word then multiedit all word with R key, then edit.
Save the file with C-c C-c or cancel with C-c C-k.

Org related
-----------
SPC-m-h to change to heading
SPC-m-i to change to item
Shift-TAB to move backward in table

Good to know
------------
SPC-h-v or C-h v to check the value or default value of any function.
SPC-TAB-TAB change workspace

