```
# help file snippets 
_____________________________________________

* moving and using help

			VIM - main help file
	
      Move around:  Use the cursor keys, or "h" to go left,
		            "j" to go down, "k" to go up, "l" to go right.
Close this window:  Use ":q<Enter>".
   Get out of Vim:  Use ":qa!<Enter>"

Jump to a subject:  Position the cursor on a tag
                    (e.g. [|bars|](|bars|)) and hit `CTRL-]`.
   With the mouse:  ":`set mouse=a`" enables mouse in xterm or GUI.
     Double-click:  mouse on a tag, e.g. [|bars|](|bars|).
    	Jump back:  Type CTRL-O.  Repeat to go back.

Get specific help:  It is possible to go directly
                    to whatever you want help on, by giving
                    an argument to the |:help| command.
 Prepend something to specify the context:  *help-context*


------------------------------------------------------------------
N is used to indicate an optional count that can be given before the
command.
-------------------------------------------------------------------
*Q_lr*		Left-right motions

|h|	N  h		left (also: CTRL-H, <BS>, or <Left> key)
|l|	N  l		right (also: <Space> or <Right> key)
|0|	   0		to first character in the line (also: <Home> key)
|^|	   ^		to first non-blank character in the line
|$|	N  $		to the last character in the line (N-1 lines lower)
			   (also: <End> key)
|g0|   g0		to first character in screen line (differs from "0"
			   when lines wrap)
|g^|   g^		to first non-blank character in screen line (differs
			   from "^" when lines wrap)
|g$| N  g$		to last character in screen line (differs from "$"
			   when lines wrap)
|gm|   gm		to middle of the screen line
|gM|   gM		to middle of the line
|bar|	N  |		to column N (default: 1)
|f|	N  f{char}	to the Nth occurrence of {char} to the right
|F|	N  F{char}	to the Nth occurrence of {char} to the left
|t|	N  t{char}	till before the Nth occurrence of {char} to the right
|T|	N  T{char}	till before the Nth occurrence of {char} to the left
|;|	N  ;		repeat the last "f", "F", "t", or "T" N times
|,|	N  ,		repeat the last "f", "F", "t", or "T" N times in
			   opposite direction

--------------------------------------------------------------------
#		Up-down motions

|k|	N  k		up N lines (also: CTRL-P and <Up>)
|j|	N  j		down N lines (also: CTRL-J, CTRL-N, <NL>, and <Down>)
|-|	N  -		up N lines, on the first non-blank character
|+|	N  +		down N lines, on the first non-blank character (also:
			   CTRL-M and <CR>)
|_|	N  _		down N-1 lines, on the first non-blank character
|G|	N  G		goto line N (default: last line), on the first
			   non-blank character
|gg| N  gg		goto line N (default: first line), on the first
			   non-blank character
|N%| N  %		goto line N percentage down in the file; N must be
			   given, otherwise it is the |%| command
|gk| N  gk		up N screen lines (differs from "k" when line wraps)
|gj| N  gj		down N screen lines (differs from "j" when line wraps)
```
