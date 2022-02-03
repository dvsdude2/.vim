# vim w/wiki
will update later
![wicked vimwiki](/images/vimpic1.png)
_____________

# THIS IS MY vim set up
## how I used it
- when roaming the interwebs and I came across information that I knew I would want to referance again I would simply 
quickly open vim wiki with my keybinding (super-k), resize to half screen, jump to webpage resize to the other half of page.
copy and paste 

# Table of Contents



<div class="python" id="org8ec4bfd">
<p>
set nocompatible                                    &ldquo;required
filetype off                                        &rdquo;required
</p>

<p>
&ldquo; set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
&rdquo; Keep Plugins between vundle#begin/end.
call vundle#begin()
</p>

<p>
Plugin &rsquo;VundleVim/Vundle.vim&rsquo;                      &ldquo;Plugin manager
Plugin &lsquo;ervandew/supertab&rsquo;                         &rdquo;Tab select
Plugin &rsquo;tpope/vim-fugitive&rsquo;                        &ldquo;Git commands
Plugin &lsquo;tpope/vim-surround&rsquo;                        &rdquo;Surround text
Plugin &rsquo;jreybert/vimagit&rsquo;                          &ldquo;Git stagging
Plugin &lsquo;tpope/vim-commentary&rsquo;                      &rdquo;Comment lines
Plugin &rsquo;jlanzarotta/bufexplorer&rsquo;                   &ldquo;Buf Explorer
Plugin &lsquo;ap/vim-buftabline&rsquo;                         &rdquo;Buf tab line
Plugin &rsquo;rbgrouleff/bclose.vim&rsquo;                     &ldquo;Close buffer
Plugin &lsquo;scrooloose/nerdtree&rsquo;                       &rdquo;Nerdtree
Plugin &rsquo;axvr/org.vim&rsquo;                              &ldquo;Org. mode syntax
Plugin &lsquo;easymotion/vim-easymotion&rsquo;                 &rdquo;Snipe vim
Plugin &rsquo;iamcco/markdown-preview.nvim&rsquo;              &ldquo;Markdown preview
Plugin &lsquo;vimwiki/vimwiki&rsquo;, { &lsquo;branch&rsquo;: &lsquo;dev&rsquo; }      &rdquo;Vim note taking
Plugin &rsquo;neoclide/coc.nvim&rsquo;, {&rsquo;branch&rsquo;: &rsquo;release&rsquo;}  &ldquo;Line completion
Plugin &lsquo;vim-lastplace&rsquo;                             &rdquo;last edited
Plugin &rsquo;tiagofumo/vim-nerdtree-syntax-highlight&rsquo;   &ldquo;Hilight Ntree
Plugin &lsquo;vim-python/python-syntax&rsquo;                  &rdquo;Python syntax
Plugin &rsquo;ap/vim-css-color&rsquo;                          &ldquo;Color previews
Plugin &lsquo;itchyny/lightline.vim&rsquo;                     &rdquo;Statusbar
Plugin &rsquo;ryanoasis/vim-devicons&rsquo;                    &ldquo;Ntree icons*last
</p>

<p>
call vundle#end()            &ldquo; required
filetype plugin indent on    &rdquo; required
&ldquo; To ignore plugin indent changes, instead use:
filetype plugin on
syntax enable
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
set encoding=UTF-8
set background=dark
set termguicolors
let g:rehash256 = 1
set guifont=Droid\ Sans\ Mono\ for\ Powerline\ Nerd\ Font\ Complete\
set path+=**                    &ldquo;Searches subdirectory.
set wildmenu                    &rdquo;Shows all matches in tab complete.
set wildmode=longest,list,full  &ldquo;should display commands
set ignorecase                  &rdquo;Case insensitive
set incsearch                   &ldquo;Incremental search
set smartcase                   &rdquo;Use case if anycaps used
set hlsearch                    &ldquo;Search highlighting
set hidden                      &rdquo;Needed to keep multi buffers open
set nobackup                    &ldquo;No auto backups
set noswapfile                  &rdquo;No swap
set number                      &ldquo;Display line numbers
set relativenumber              &rdquo;Display relative line numbers
set clipboard=unnamedplus       &ldquo;Clipboard access to all programs.
set so=7                        &rdquo;Keep 7 lines visable when scrolling
set history=999                 &ldquo;Increase history (default = 20)
set autoread                    &rdquo;reload files if changed externally
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; mapped leader to &lt;&rsquo;&gt;
let mapleader = &rdquo;&rsquo;&ldquo;
&rdquo; changes cursor to a bar when in insert mode
let &amp;t<sub>SI</sub> = &ldquo;\&lt;Esc&gt;]50;CursorShape=1\x7&rdquo;
let &amp;t<sub>EI</sub> = &ldquo;\&lt;Esc&gt;]50;CursorShape=0\x7&rdquo;
&ldquo; open command edit window everytime
nnoremap : q:i
nnoremap / q/i
&rdquo; =&gt; Open terminal inside Vim
nnoremap &lt;Leader&gt;tt :vert term&lt;CR&gt;
&ldquo; quickly open a buffer for scribble
noremap &lt;leader&gt;q :e ~/buffer&lt;cr&gt;
&rdquo; close buffer not window
nnoremap Q :Bclose&lt;CR&gt;
&ldquo; buffer tabbing
noremap &lt;Leader&gt;bb :bnext&lt;CR&gt;
noremap &lt;Leader&gt;bg :bprev&lt;CR&gt;
&rdquo; Underline the current line, based on its length.
noremap &lt;silent&gt; &lt;leader&gt;ul mmyypVr-&lt;Esc&gt;`m
&ldquo; Switch to current dir
noremap &lt;Leader&gt;scd :cd %:p:h&lt;cr&gt;
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; Quick back to normal mode
inoremap jh &lt;esc&gt;
inoremap jj &lt;esc&gt;
&rdquo; yank to end of line
noremap Y y$
&ldquo; Quick write to file
noremap &lt;leader&gt;&lt;space&gt; :w!&lt;cr&gt;
&rdquo; quickly add ` around a word
nnoremap \` i`&lt;Esc&gt;ea`&lt;Esc&gt;
&ldquo; Duplicate lines
nnoremap &lt;C-S-Up&gt; YP
nnoremap &lt;C-S-Down&gt; YP
&rdquo; Jump to the start or end of line without leaving the home row
noremap H ^
noremap L $
&ldquo;delete all lines in the current buffer
nnoremap &lt;leader&gt;daa ggdG
&rdquo; yank all lines in current buffer
nnoremap yY :%yank &lt;c-r&gt;=v:register&lt;cr&gt;&lt;cr&gt;
&ldquo; Quickly add empty lines
nnoremap &lt;silent&gt; &lt;F10&gt; :&lt;C-u&gt;put!=repeat(nr2char(10),v:count)&lt;Bar&gt;execute &rdquo;&rsquo;]+1&ldquo;&lt;CR&gt;
nnoremap &lt;silent&gt; &lt;F9&gt; :&lt;C-u&gt;put =repeat(nr2char(10),v:count)&lt;Bar&gt;execute &rdquo;&rsquo;[-1&ldquo;&lt;CR&gt;
&rdquo; nnoremap &lt;silent&gt; &lt;F10&gt; :&lt;c-u&gt;put! =repeat(nr2char(10), v:count1)&lt;cr&gt;&rsquo;[
&ldquo; nnoremap &lt;silent&gt; &lt;F9&gt; :&lt;c-u&gt;put =repeat(nr2char(10), v:count1)&lt;cr&gt;
&rdquo; Quickly move current line
nnoremap [e  :&lt;c-u&gt;execute &rsquo;move -1-&rsquo;. v:count1&lt;cr&gt;
nnoremap ]e  :&lt;c-u&gt;execute &rsquo;move +&rsquo;. v:count1&lt;cr&gt;
&ldquo; visualy select &amp; move lines with &lt;shift&gt;
xnoremap K :move &rsquo;&lt;-2&lt;CR&gt;gv-gv
xnoremap J :move &rsquo;&gt;+1&lt;CR&gt;gv-gv
&rdquo; Split line at cursor
nnoremap &lt;silent&gt; S :keeppatterns substitute/\s*\%#\s*/\r/e &lt;bar&gt; normal! <code>=&lt;CR&gt;
==============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; ctrl-r in v mod will be asked for replacement
vnoremap &lt;C-r&gt; &rdquo;hy:%s/&lt;C-r&gt;h//gc&lt;left&gt;&lt;left&gt;&lt;left&gt;
&ldquo; press * or # to search for the current selection
vnoremap &lt;silent&gt; * :call VisualSearch(&lsquo;f&rsquo;)&lt;CR&gt;
vnoremap &lt;silent&gt; # :call VisualSearch(&lsquo;b&rsquo;)&lt;CR&gt;
&rdquo; after search hit Ctrl-x to remove highlight
nnoremap &lt;silent&gt; &lt;C-x&gt; :nohlsearch&lt;CR&gt;&lt;CR&gt;
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
set splitbelow splitright
set expandtab                   &ldquo; Use spaces instead of tabs.
set shiftwidth=4                &rdquo; One tab <code>= four spaces.
set tabstop=4                   " One tab =</code> four spaces.
&ldquo; Remap splits navigation to just CTRL + hjkl
nnoremap &lt;C-h&gt; &lt;C-w&gt;h
nnoremap &lt;C-j&gt; &lt;C-w&gt;j
nnoremap &lt;C-k&gt; &lt;C-w&gt;k
nnoremap &lt;C-l&gt; &lt;C-w&gt;l
&rdquo; Make adjusing split sizes a bit more friendly
noremap &lt;silent&gt; &lt;C-Left&gt; :vertical resize +3&lt;CR&gt;
noremap &lt;silent&gt; &lt;C-Right&gt; :vertical resize -3&lt;CR&gt;
noremap &lt;silent&gt; &lt;C-Up&gt; :resize +3&lt;CR&gt;
noremap &lt;silent&gt; &lt;C-Down&gt; :resize -3&lt;CR&gt;
&ldquo; Change 2 split windows from vert to horiz or horiz to vert
nnoremap &lt;Leader&gt;th &lt;C-w&gt;t&lt;C-w&gt;H
nnoremap &lt;Leader&gt;tk &lt;C-w&gt;t&lt;C-w&gt;K
&rdquo; Removes pipes | that act as seperators on splits
set fillchars+=vert:\
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; highlight LineNr           ctermfg=8    ctermbg=none    cterm=none
&rdquo; highlight CursorLineNr     ctermfg=8    ctermbg=8       cterm=none
&ldquo; highlight VertSplit        ctermfg=0    ctermbg=8       cterm=none
&rdquo; highlight Statement        ctermfg=2    ctermbg=none    cterm=none
&ldquo; highlight Directory        ctermfg=4    ctermbg=none    cterm=none
highlight StatusLine       ctermfg=7    ctermbg=8       cterm=none
highlight StatusLineNC     ctermfg=7    ctermbg=8       cterm=none
highlight BufTabLineHidden   ctermfg=239    ctermbg=236
highlight BufTabLineFill     ctermfg=220    ctermbg=236
highlight BufTabLineActive   ctermfg=220    ctermbg=236
&rdquo; highlight NERDTreeClosable ctermfg=2
&ldquo; highlight NERDTreeOpenable ctermfg=8
&rdquo; highlight Comment          ctermfg=4    ctermbg=none    cterm=italic
&ldquo; highlight Constant         ctermfg=12   ctermbg=none    cterm=none
&rdquo; highlight Special          ctermfg=4    ctermbg=none    cterm=none
&ldquo; highlight Identifier       ctermfg=6    ctermbg=none    cterm=none
&rdquo; highlight PreProc          ctermfg=5    ctermbg=none    cterm=none
&ldquo; highlight String           ctermfg=12   ctermbg=none    cterm=none
&rdquo; highlight Number           ctermfg=1    ctermbg=none    cterm=none
&ldquo; highlight Function         ctermfg=1    ctermbg=none    cterm=none
&rdquo; highlight WildMenu         ctermfg=0       ctermbg=80      cterm=none
&ldquo; highlight Folded           ctermfg=103     ctermbg=234     cterm=none
&rdquo; highlight FoldColumn       ctermfg=103     ctermbg=234     cterm=none
</p>

<p>
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; sources .vimrc after every write or save
autocmd BufWritePost ~/.vim/vimrc. source ~/.vim/vimrc.
&rdquo; sources .vimrc after every write or save
&ldquo; autocmd! bufwritepost ~/.vim/vimrc. source ~/.vim/vimrc.
&rdquo; open vimrc
nmap &lt;leader&gt;e :e! ~/.vim/vimrc.&lt;cr&gt;
&ldquo; open vimrc in vertical split
nmap &lt;leader&gt;ev :vsplit ~/.vim/vimrc.&lt;cr&gt;
&rdquo; source vimrc
nmap &lt;leader&gt;sv :source $MYVIMRC&lt;cr&gt;
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; Uncomment to autostart the NERDTree
&rdquo; autocmd vimenter * NERDTree
nnoremap &lt;C-n&gt; :NERDTreeToggle&lt;CR&gt;
let g:NERDTreeDirArrowExpandable = &rsquo;►&rsquo;
let g:NERDTreeDirArrowCollapsible = &rsquo;▼&rsquo;
let NERDTreeShowLineNumbers=1
let g:NERDTreeQuitOnOpen=0
let NERDTreeShowHidden=1
let NERDTreeMinimalUI = 1
let g:NERDTreeWinSize=38
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; don&rsquo;t pass messages to |ins-completion-menu|.
set shortmess+=c
&rdquo; Use &lt;cr&gt; to confirm completion
inoremap &lt;expr&gt; &lt;cr&gt; pumvisible() ? &ldquo;\&lt;C-y&gt;&rdquo; : &ldquo;\&lt;C-g&gt;u\&lt;CR&gt;&rdquo;
&ldquo; To make &lt;cr&gt; select the first completion item
inoremap &lt;silent&gt;&lt;expr&gt; &lt;cr&gt; pumvisible() ? coc#<sub>select</sub><sub>confirm</sub>() : &rdquo;\&lt;C-g&gt;u\&lt;CR&gt;&ldquo;
&rdquo; use tab to make selections &#x2026;was taken down for supertab
&ldquo; noremap! &lt;silent&gt;&lt;expr&gt; &lt;Tab&gt;
&rdquo;       \ pumvisible() ? &ldquo;\&lt;C-n&gt;&rdquo; :
&ldquo;       \ &lt;SID&gt;check<sub>back</sub><sub>space</sub>() ? &rdquo;\&lt;Tab&gt;&ldquo; :
&rdquo;       \ coc#refresh()
let g:SuperTabDefaultCompletionType = &ldquo;&lt;c-n&gt;&rdquo;
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
let g:mkdp<sub>auto</sub><sub>start</sub> = 0                    &ldquo; Turns off auto preview
&rdquo; specify browser to open preview page       &ldquo; default= &lsquo;&rsquo;
let g:mkdp<sub>browser</sub> = &lsquo;surf&rsquo;                  &rdquo; Uses surf for preview
&ldquo; Previews .md files
nnoremap &lt;Leader&gt;mk &lt;Plug&gt;MarkdownPreview
&rdquo; Kills the preview
nnoremap &lt;Leader&gt;nm &lt;Plug&gt;MarkdownPreviewStop
&ldquo; Preview toggle
nnoremap &lt;Leader&gt;mp &lt;Plug&gt;MarkdownPreviewToggle
<code>==============================================================</code>
</p>

<p>
<code>==============================================================</code>
&ldquo; The lightline.vim theme
let g:lightline = {
\ &lsquo;colorscheme&rsquo;: &lsquo;deus&rsquo;,
\ &lsquo;active&rsquo;: {
\   &lsquo;left&rsquo;: [ [ &lsquo;mode&rsquo;, &lsquo;paste&rsquo; ],
\             [ &lsquo;readonly&rsquo;, &lsquo;fugitive&rsquo;, &lsquo;filename&rsquo;, &lsquo;modified&rsquo; ] ],
\   &lsquo;right&rsquo;: [ [ &lsquo;lineinfo&rsquo; ],
\              [ &lsquo;percent&rsquo; ],
\              [ &lsquo;fileformat&rsquo;, &lsquo;fileencoding&rsquo;, &lsquo;filetype&rsquo; ] ]
\ },
\ &lsquo;component&rsquo;: {
\   &lsquo;lineinfo&rsquo;: &lsquo; %L  %3l:%-2v&rsquo;,
\   &lsquo;modified&rsquo;: &rsquo;[%M]&rsquo;
\ },
\ &lsquo;component<sub>function</sub>&rsquo;: {
\   &lsquo;readonly&rsquo;: &lsquo;LightlineReadonly&rsquo;,
\   &lsquo;fugitive&rsquo;: &lsquo;LightlineFugitive&rsquo;
\ },
\ &lsquo;separator&rsquo;: { &lsquo;left&rsquo;: &lsquo;&rsquo;, &lsquo;right&rsquo;: &lsquo;&rsquo; },
\ &lsquo;subseparator&rsquo;: { &lsquo;left&rsquo;: &lsquo;&rsquo;, &lsquo;right&rsquo;: &lsquo;&rsquo; }
\ }
function! LightlineReadonly()
return &amp;readonly ? &lsquo;&rsquo; : &lsquo;&rsquo;
endfunction
function! LightlineFugitive()
if exists(&lsquo;*fugitive#head&rsquo;)
let branch = fugitive#head()
return branch !=# &lsquo;&rsquo; ? &lsquo;&rsquo;.branch : &lsquo;&rsquo;
endif
return &lsquo;&rsquo;
endfunction
</p>

<p>
&ldquo; Always show statusline
set laststatus=2
&rdquo; Keeps insert status from showing up under statusbar.
set noshowmode
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; Shows buf. labels only if two or more are open
let g:buftabline<sub>show</sub> = 1
&rdquo; Switch buffers by their left to right number =2
let g:buftabline<sub>numbers</sub> = 2
&ldquo; switch buffers by their ordinal number
&rdquo; buftabline<sub>numbers</sub> = 2
nmap &lt;leader&gt;1 &lt;Plug&gt;BufTabLine.Go(1)
nmap &lt;leader&gt;2 &lt;Plug&gt;BufTabLine.Go(2)
nmap &lt;leader&gt;3 &lt;Plug&gt;BufTabLine.Go(3)
nmap &lt;leader&gt;4 &lt;Plug&gt;BufTabLine.Go(4)
nmap &lt;leader&gt;5 &lt;Plug&gt;BufTabLine.Go(5)
</p>

<p>
&ldquo; always switches to the last buffer
nmap &lt;leader&gt;0 &lt;Plug&gt;BufTabLine.Go(-1)
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
let g:EasyMotion<sub>do</sub><sub>mapping</sub> = 0 # Disable default mappings
</p>

<p>
&ldquo; Jump to anywhere with minimal keystrokes, just one key binding.
&rdquo; `s{char}{label}`
&ldquo; nmap s &lt;Plug&gt;(easymotion-overwin-f)
&rdquo; or
&ldquo; `s{char}{char}{label}`
&rdquo; Need one more keystroke, but on average, may be more comfortable.
nmap s &lt;Plug&gt;(easymotion-overwin-f2)
</p>

<p>
&ldquo; Turn on case-insensitive feature
let g:EasyMotion<sub>smartcase</sub> = 1
</p>

<p>
&ldquo; JK motions: Line motions
nmap &lt;Leader&gt;j &lt;Plug&gt;(easymotion-j)
nmap &lt;Leader&gt;k &lt;Plug&gt;(easymotion-k)
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; Toggle spell-checking.
noremap &lt;silent&gt; &lt;leader&gt;sc :set spell!&lt;CR&gt;
&rdquo; Next spelling error
nnoremap &lt;silent&gt; &lt;f5&gt; ]s
&ldquo; Previous spelling error
nnoremap &lt;silent&gt; &lt;f6&gt; [s
&rdquo; Try to lazily fix the current spelling mistake.
noremap &lt;silent&gt; &lt;f7&gt; 1z=
&ldquo; Suggest a spelling
noremap &lt;silent&gt; &lt;f8&gt; z=
<code>=============================================================</code>
<code>=&gt; VimWiki
==============================================================</code>
&rdquo; tells wiki to use markdown syntax
let g:vimwiki<sub>list</sub> = [{&rsquo;path&rsquo;: &rsquo;~/.vim/vimwiki/&rsquo;,
\ &rsquo;syntax&rsquo;: &rsquo;markdown&rsquo;, &rsquo;ext&rsquo;: &rsquo;.md&rsquo;}]
</p>

<p>
&ldquo; this allows tab to work with coc menu selection
au filetype vimwiki silent! iunmap &lt;buffer&gt; &lt;Tab&gt;
&rdquo; set text to wrap
&ldquo; set textwidth=68
&rdquo; this should highlight when line is overlenth
augroup vimrc<sub>autocmds</sub>
autocmd BufEnter * highlight OverLength ctermbg=darkgrey guibg=#592929
autocmd BufEnter * match OverLength <i>\%70v.*</i>
augroup END
:hi VimwikiHeader1 guifg=#FF00FF
:hi VimwikiHeader2 guifg=#0000FF
:hi VimwikiHeader3 guifg=#00FF00
:hi VimwikiHeader4 guifg=#FF0000
:hi VimwikiHeader5 guifg=#00FFFF
:hi VimwikiHeader6 guifg=#FFFF00
<code>=============================================================</code>
</p>

<p>
<code>=============================================================</code>
&ldquo; makes folds cleaner
let g:org<sub>clean</sub><sub>folds</sub> = 1
&rdquo; move vertically by visual line (don&rsquo;t skip wrapped lines)
nnoremap &lt;silent&gt; k gk
nnoremap &lt;silent&gt; j gj
nnoremap &lt;silent&gt; &lt;Up&gt; gk
nnoremap &lt;silent&gt; &lt;Down&gt; gj
&ldquo; Abbreviate error messages
&rdquo; set shortmess=a
&ldquo; Add time stamp
nnoremap &lt;F4&gt; &rdquo;=strftime(&ldquo;%a, %H:%M:%S&rdquo;)&lt;CR&gt;P
inoremap &lt;F4&gt; &lt;C-R&gt;=strftime(&ldquo;%a, %H:%M:%S&rdquo;)&lt;CR&gt;
&ldquo; Use python syntax as a default
let g:python<sub>highlight</sub><sub>all</sub> = 1
&rdquo; Remove some stuff from gui version
set guioptions-=m  &ldquo;remove menu bar
set guioptions-=T  &rdquo;remove toolbar
set guioptions-=r  &ldquo;remove right-hand scroll bar
set guioptions-=L  &rdquo;remove left-hand scroll bar
</p>

</div>


