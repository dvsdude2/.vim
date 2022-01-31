===============================================================================
# TL;DR                                                         *vimagit-TL;DR*
----------

This is the minimal required set of command you must know to start playing
with vimagit. See |vimagit-commands| for a complete description.

To simply test vimagit, modify/add/delete/rename some files in a git
repository and open vim.

> `:Magit`
[Open](Magit) magit buffer with :Magit command.

> `Ctrl-n`
Jump to [next hunk](don't need for just one) with <C-n>.
The cursor should be on the header of a hunk.

> `S`
If the hunk is in "Unstage changes" section, press S in Normal mode: the
[hunk is now staged](stage a hunk), and appears in "Staged changes" section. The opposite is
also possible, i.e. unstage a hunk from "Staged section".

If you move the **cursor** to the `file header`
and
press > `S`, [the whole file is staged](.)

> `CC`
Once you have stage all the required changes, type CC.
A new section [Commit message](insert mode) appears, move cursor to it.
Type your commit message, in Insert mode this time.
Once it's done, write or save your commit message with
`:w` (or :wq, `ZZ`).

Voila! you created your first commit with vimagit!

===============================================================================
