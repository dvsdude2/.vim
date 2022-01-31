```
# random config option 
_________________________

==================================================================
Things I've added section
===================================================================

" Change directory to current file dir
--------------------------------------
nnoremap <Leader>cd :cd %:p:h<CR>:pwd<CR>


Press F4 in normal mode or in insert mode to insert the current
datestamp: :help i_CTRL-R
-------------------------

:nnoremap <F4> "=strftime("%c")<CR>P
:inoremap <F4> <C-R>=strftime("%c")<CR>

In the example above, the uppercase P at the end inserts
before the current character, which allows datestamps inserted
at the beginning of an existing line.
Other 'put' commands may be more useful for you:
:help p :help P :help gp :help gP

Some strftime() format string examples
Format String              Example output
-------------              --------------
%c                         Thu 27 Sep 2007 07:37:42 AM EDT (depends on locale)
%a %d %b %Y                Thu 27 Sep 2007
%b %d, %Y                  Sep 27, 2007
%d/%m/%y %H:%M:%S          27/09/07 07:36:32
%H:%M:%S                   07:36:44
%T                         07:38:09
%m/%d/%y                   09/27/07
%y%m%d                     070927
%x %X (%Z)                 09/27/2007 08:00:59 AM (EDT)
%Y-%m-%d                   2016-11-23
%F                         2016-11-23 (works on some systems)

" Yank from current cursor position to end of line__
map Y y$

" Switch to current dir
map <Leader>cdi :cd %:p:h<cr>

" Quickly move current line
nnoremap [e  :<c-u>execute 'move -1-'. v:count1<cr>
nnoremap ]e  :<c-u>execute 'move +'. v:count1<cr>

"delete all lines in the current buffer
nmap <leader>daa ggdG
nmap <leader>caa ggVG

== Quickly open a buffer for scribble ==
map <leader>q :e ~/buffer<cr>
🌐
== should keep cursor from bttm line when moving ==
set so=7                   " Keep 7 lines visible when scrolling

== Vim search and replace selected text ==
Try execute the following or put in into your .vimrc

vnoremap <C-r> "hy:%s/<C-r>h//gc<left><left><left>

By pressing ctrl+r in visual mode,
you will be prompted to enter text to replace with.
Press enter and then confirm each change with y or decline with n.
This command will override your register h
so you can choose other one 
(change h in the command above to another lower case letter) 
that you don't use.


"""""""""""""""""""""""""""""
" => Visual mode related
""""""""""""""""""""""""""""""
" Visual mode pressing * or # searches for the current selection
" Super useful! From an idea by Michael Naumann
vnoremap <silent> * :<C-u>call VisualSelection('', '')<CR>/<C-R>=@/<CR><CR>
vnoremap <silent> # :<C-u>call VisualSelection('', '')<CR>?<C-R>=@/<CR><CR>


" move vertically by visual line (don't skip wrapped lines)
nmap j gj
nmap k gk


" you press * or # to search for the current selection
vnoremap <silent> * :call VisualSearch('f')<CR>
vnoremap <silent> # :call VisualSearch('b')<CR>


" yank all lines in current buffer
nnoremap yY :%yank <c-r>=v:register<cr><cr>


 " Quickly move current line
nnoremap [e  :<c-u>execute 'move -1-'. v:count1<cr>
nnoremap ]e  :<c-u>execute 'move +'. v:count1<cr>


===================================================================
# unsorted mess below 
------------------------------------------------------------------
  "+"   -  Move forward to the first character on the next line
  "-"   -  Move backwards to first character on  previous line
  "D"   -  Delete until end of line 
  "C"   -  Delete (change) cursor to end of line, enter insert mode
### VISUAL MODE
o        -   Switch cursor from first & last character
             of highlighted block while in visual mode
~        -   Swap case under selection
<<       -   Shift lines to left
>>       -   Shift lines to right

cool new keybindings
- " Get rid of the delay when pressing O (for example)
" http://stackoverflow.com/questions/2158516/vim-delay-before-o-opens-a-new-line
set timeout timeoutlen=1000 ttimeoutlen=100


====== snippets command config 🌐 ======
Created Saturday 21 August 2021
🌐

== Paste in insert mode?#1 ==
No not directly. What you can do though is quickly exit insert mode
for a single normal mode operation with Ctrl-O and then
paste from there which will end by putting you back in insert mode.

Key Combo: Ctrl-O p

== Paste in insert mode?#2 ==
While in insert mode hit CTRL-R {register}

Examples:
CTRL-R * will insert in the contents of the clipboard
CTRL-R " (the unnamed register) inserts the last delete or yank.
To find this in vim's help type :h i_ctrl-r

set wmh=0                   " allow window to be 0 lines high


== Edit another file in the same directory as the current file ==
" Uses expression to extract path from current file's path
map <Leader>e :e <C-R>=expand("%:p:h") . '/'<CR>
map <Leader>s :split <C-R>=expand("%:p:h") . '/'<CR>
map <Leader>v :vnew <C-R>=expand("%:p:h") . '/'<CR>

set backspace=eol,start,indent


== To confirm each substitution, use the c flag: ==
:s/foo/bar/gc

Examples:
**Comment lines (add # before the line) from 5 to 20:**
:5,20s/^/#/

**Uncomment lines from 5 to 20, revert the previous changes:**
:5,20s/^#//


=== Spell checking ===
See vimcast #19 as an introduction:
http://vimcasts.org/episodes/spell-checking/

Assuming that you have the following in .vimrc:

nnoremap <silent> <leader>s :set spell!<cr>
<leader>s Toggle Spelling
]s       Next spelling mistake
[s       Previous spelling mistake
z=       Give Suggestions (prepent 1, use first suggestions automatically)
zg       Add misspelled to spellfile
zug      Remove word from spellfile


=== jump to end of line while in Insert Mode ===

C-e
inoremap <C-e> <C-o>$

inoremap maps a key combination for insert mode
<C-e> is the keybinding I am creating.
<C-o> is a command that switches vim to normal mode for one command.
$ jumps to the end of the line and switched back to insert mode.
C-a

allows you to jump to beginning of a line while in insert mode.
inoremap <C-a> <C-o>0

=== *Using inoremap instead of imap ===
These keybindings could also be written using imap
instead of inoremap.
The difference between the two commands,
is that inoremap is non-recursive.
So if somewhere in your .vimrc or a plugin C-o is remapped with:
imap <C-o> <esc>O
Then the above remappings of <C-e> (with imap)
would be changed also and no longer work.
So in general it is best to remap
with the nore (non-recursive) versions:
noremap nnoremap inoremap vnoremap


=== Key sequences ===
Replace a word in a number of occurrences with 'bar';
use word under cursor (* or /foo)
' * cw bar ESC n . '

'*' word under cursor 'foo'
cw    change word (enter insert mode)
bar   typed new word 'bar'
ESC   exit insert mode
n     next occurrence
.     repeat previous command 
Insert 3 times "Help!": Help! Help! Help!
3i Help!_ ESC

=== Search for selected text ===
__<select> y / C-r0__

<select> Select text in VISUAL mode (v)
y        Yank selection
/        Search for
C-r0     Press Ctrl-R and 0 to paste in

=== Comment out selection ===
__C-v <select> # ESC ESC__

C-v   Enter VISUAL block mode
<sel> Select lines
 
== What is the history file called? Where is it stored? ==
It is populated at startup from the .viminfo file

-dudes name scottguthart---------------------------

filetype plugin indent on
syntax on
   if
    need_to_install_plugins == 1
	echo "Installing plugins..."
	silent! PlugInstall
	echo "Done!"
	q
endif


" tags
map <leader>t :TagbarToggle<CR>


Plug 'ap/vim-buftabline'
Plug 'airblade/vim-gitgutter'
Plug 'Xuyuanp/nerdtree-git-plugin'
Plug 'jiangmiao/auto-pairs'
Plug 'dense-analysis/ale'
Plug 'majutsushi/tagbar'
Plug 'vim-scripts/indentpython.vim'
Plug 'lepture/vim-jinja'
Plug 'pangloss/vim-javascript'
Plug 'alvan/vim-closetag'
Plug 'maxmellon/vim-jsx-pretty'

--------------------
dudes name is strider
" Get rid of the delay when pressing O (for example)
" http://stackoverflow.com/questions/2158516/vim-delay-before-o-opens-a-new-line
set timeout timeoutlen=1000 ttimeoutlen=100

" easier moving of code blocks
" Try to go into visual mode (v),
thenselect several lines of code here and
" then press ``>`` several times.
vnoremap < <gv  " better indentation
xnoremap > >gv  " better indentation

" Move visual block
xnoremap R :m '>+1<CR>gv=gv
xnoremap T :m '<-2<CR>gv=gv


" \F to startup an ack search
map <leader>fa :Ack<space>


" _ Vim {{{
augroup ft_vim
  au!

  au FileType vim setlocal foldmethod=marker
  au FileType help setlocal textwidth=80
  au BufWinEnter *.txt if &ft == 'help' | wincmd L | endif
augroup END

" }}}



an autocommand to generate links each time the diary index is open.

command! Diary VimwikiDiaryIndex
augroup vimwikigroup
    autocmd!
    " automatically update links on read diary
    autocmd BufRead,BufNewFile diary.wiki VimwikiDiaryGenerateLinks
augroup end

"git vimwiki 
augroup vimwiki
au! BufWritePost ~/vimwiki/* !git add "%";git commit -m "Auto commit of %:t." "%"
augroup END


things I'm not sure of below line
-----------------------------------------

" Quickly add empty lines
nnoremap <silent><A-j> :set paste<CR>m`o<Esc>``:set nopaste<CR>
nnoremap <silent><A-k> :set paste<CR>m`O<Esc>``:set nopaste<CR>

" Quickly add empty lines
nnoremap [<space>  :<c-u>put! =repeat(nr2char(10), v:count1)<cr>'[
nnoremap ]<space>  :<c-u>put =repeat(nr2char(10), v:count1)<cr>

" vv to generate new vertical split
nnoremap <silent> vv <C-w>v

"" Quicksave command
noremap <C-Z> :update<CR>
vnoremap <C-Z> <C-C>:update<CR>
inoremap <C-Z> <C-O>:update<CR>
nnoremap <Leader>w :w<CR>

" Enter visual line mode with <Space><Space>:
nmap <Leader><Leader><Leader> V

" Quick quit command
noremap <Leader>e :quit<CR>  " Quit current window
noremap <Leader>E :qa!<CR>   " Quit all windows



" split vertically with <leader> v
" split horizontally with <leader> s
nmap <Leader>vs :vsplit<CR> <C-w><C-w>
nmap <Leader>sp :split<CR> <C-w><C-w>

-----------------------------------------------------------------
```
