```

https://gist.github.com/sllide/9d630d2ce548bf84e773e84a7b349a17
"lightline
  let g:lightline = {}
  let g:lightline.colorscheme = 'gruvbox'
  let g:lightline.separator = { 'left': '', 'right': '' }
  let g:lightline.subseparator = { 'left': '', 'right': '' }
  let g:lightline.tabline          = {'left': [['buffers']], 'right':[[]]}
  let g:lightline.component_expand = {'buffers': 'lightline#bufferline#buffers'}
  let g:lightline.component_type   = {'buffers': 'tabsel'}
  "header
    source ~/.config/nvim/header.vim 
    
"lightline bufferline
  let g:lightline#bufferline#unicode_symbols = 1
  let g:lightline#bufferline#shorten_path = 0



https://gist.github.com/x86taha/6943511d131935416161f815f36960a8
Plug 'itchyny/lightline.vim'
let g:lightline = {
    \ 'colorscheme': 'landscape',
    \ 'active': {
    \   'left': [ [ 'mode', 'paste' ],
    \             [ 'readonly', 'fugitive', 'filename', 'modified' ] ],
    \   'right': [ [ 'lineinfo' ],
      \              [ 'percent' ],
      \              [ 'fileformat', 'fileencoding', 'filetype' ] ]
    \ },
    \ 'component': {
    \   'lineinfo': ' %L  %3l:%-2v',
    \   'modified': '[%M]'
    \ },
    \ 'component_function': {
    \   'readonly': 'LightlineReadonly',
    \   'fugitive': 'LightlineFugitive'
    \ },
    \ 'separator': { 'left': '', 'right': '' },
    \ 'subseparator': { 'left': '', 'right': '' }
    \ }
function! LightlineReadonly()
  return &readonly ? '' : ''
endfunction
function! LightlineFugitive()
  if exists('*fugitive#head')
    let branch = fugitive#head()
    return branch !=# '' ? ''.branch : ''
  endif
  return ''
endfunction


Plug 'mengelbrecht/lightline-bufferline'
    let g:lightline.tabline          = {'left': [['buffers']], 'right': [[ 'close' ]]}
    let g:lightline.component_expand = {'buffers': 'lightline#bufferline#buffers'}
    let g:lightline.component_type   = {'buffers': 'tabsel'}
    let g:lightline#bufferline#show_number=1
    let g:lightline#bufferline#unicode_symbols=1
    let g:lightline#bufferline#enable_devicons=1




"------------------------------------------
" Lightline & bufferline 
"------------------------------------------
set showtabline=2  " always show tabline
set noshowmode
let g:lightline = {}
let g:lightline.colorscheme = 'wombat'
let g:lightline.active =  {'left':[['mode', 'paste'], ['gitbranch', 'readonly', 'filename', 'modified']]}
let g:lightline.component = {'lineinfo': ' %3l:%-2v'}
let g:lightline.component_function = {'gitbranch': 'fugitive#head'}
"let g:lightline.separator       = {'left': '', 'right': ''}
let g:lightline.subseparator        = {'left': '', 'right': ''}
let g:lightline.tabline             = {'left': [['buffers']], 'right': []}
let g:lightline.component_expand    = {'buffers': 'lightline#bufferline#buffers'}
let g:lightline.component_type      = {'buffers': 'tabsel'}

let g:lightline#bufferline#show_number          = 2
let g:lightline#bufferline#unnamed              = '[No Name]'
let g:lightline#bufferline#filename_modifier    = ':t'
let g:lightline#bufferline#modified             = '✎'
let g:lightline#bufferline#number_map           = { 0: '⁰', 1: '¹', 2: '²', 3: '³', 4: '⁴', 5: '⁵', 6: '⁶', 7: '⁷', 8: '⁸', 9: '⁹' }

nmap <leader>1 <Plug>lightline#bufferline#go(1)
nmap <leader>2 <Plug>lightline#bufferline#go(2)
nmap <leader>3 <Plug>lightline#bufferline#go(3)
nmap <leader>4 <Plug>lightline#bufferline#go(4)
nmap <leader>5 <Plug>lightline#bufferline#go(5)
nmap <leader>6 <Plug>lightline#bufferline#go(6)
nmap <leader>7 <Plug>lightline#bufferline#go(7)
nmap <leader>8 <Plug>lightline#bufferline#go(8)
nmap <leader>9 <Plug>lightline#bufferline#go(9)
nmap <leader>0 <Plug>lightline#bufferline#go(10)
function! LightlineLineinfo()
  if &ft ==? 'fzf' | return '' | endif
  if &ft ==? 'nerdtree' | return '' | endif


- clippings 2
--------------
  return printf("%3d:%-2d", line('.'), col('.'))
endfunction
```
