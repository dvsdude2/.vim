readme.md
ctrlp.vim
Full path fuzzy file, buffer, mru, tag, ... finder for Vim.

ctrlp

Basic Usage
Run :CtrlP or :CtrlP [starting-directory] to invoke CtrlP in find file mode.
Run :CtrlPBuffer or :CtrlPMRU to invoke CtrlP in find buffer or find MRU file mode.
Run :CtrlPMixed to search in Files, Buffers and MRU files at the same time.
Check :help ctrlp-commands and :help ctrlp-extensions for other commands.

Once CtrlP is open:

to purge the cache                Press <F5> 
to cycle between modes.           Press <c-f> and <c-b>
to switch to filename only.       Press <c-d>
to switch to regexp mode.         Press <c-r> 
to navigate the result list.      Use <c-j>, <c-k> or the arrow keys 
to open in a tab or in a split.   Use <c-t> or <c-v>, <c-x> 
to select next/prev in history.   Use <c-n>, <c-p> 
to create a new file              Use <c-y>
to mark/unmark multiple files     Use <c-z> and <c-o> to open them.
Run :help ctrlp-mappings or submit ? in CtrlP for more mapping help.

Submit two or more dots .. to go up the directory tree by one or multiple levels.
End the input string with a colon :
followed by a command to execute it on the opening file(s):
Use :25 to jump to line 25.
Use : diffthis when opening multiple files to run :
diffthis on the first 4 files.

Basic Options
Change the default mapping and the default command to invoke CtrlP:

let g:ctrlp_map = '<c-p>'
let g:ctrlp_cmd = 'CtrlP'
When invoked without an explicit starting directory,
CtrlP will set its local working directory according to this variable:

Check :help ctrlp-options for other options.




----------------------------------------
Once inside the prompt:~

  <c-d>
    Toggle between full-path search and filename only search.
    Note: in filename mode, the prompt's base is '>d>' instead of '>>>'

  <c-r>                                                    *'ctrlp-fullregexp'*
    Toggle between the string mode and full regexp mode.
    Note: in full regexp mode, the prompt's base is 'r>>' instead of '>>>'

    See also: |input-formats| (guide) and |g:ctrlp_regexp_search| (option).

  <c-f>, 'forward'
  <c-up>
    Scroll to the 'next' search mode in the sequence.

  <c-b>, 'backward'
  <c-down>
    Scroll to the 'previous' search mode in the sequence.

  <tab>                                                *'ctrlp-autocompletion'*
    Auto-complete directory names under the current working directory inside
    the prompt.

  <s-tab>
    Toggle the focus between the match window and the prompt.

  <esc>,
  <c-c>,
  <c-g>
    Exit CtrlP.

Moving:~

  <c-j>,
  <down>
    Move selection down.

  <c-k>,
  <up>
    Move selection up.

  <c-a>
    Move the cursor to the 'start' of the prompt.

  <c-e>
    Move the cursor to the 'end' of the prompt.

  <c-h>,
  <left>,
  <c-^>
    Move the cursor one character to the 'left'.

  <c-l>,
  <right>
    Move the cursor one character to the 'right'.
