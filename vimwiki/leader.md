```
# nmap leader


== nmap <leader> ==
n  ["          *@:call search('\%(^\s*".*\n\)\%(^\s*"\)\@!', "bW")<CR>
n  []          *@m':call search('^\s*end\(f\%[unction]\|def\)\>', "bW")<
CR>
n  [[          *@m':call search('^\s*\(fu\%[nction]\|def\)\>', "bW")<CR>
n  ]"          *@:call search('^\(\s*".*\n\)\@<!\(\s*"\)', "W")<CR>
n  ][          *@m':call search('^\s*end\(f\%[unction]\|def\)\>', "W")<C
R>
n  ]]          *@m':call search('^\s*\(fu\%[nction]\|def\)\>', "W")<CR>
n  <CR>        * :nohlsearch<CR><CR>
n  'w'm          <Plug>VimwikiMakeTomorrowDiaryNote
n  'w'y          <Plug>VimwikiMakeYesterdayDiaryNote
n  'w't          <Plug>VimwikiTabMakeDiaryNote
n  'w'w          <Plug>VimwikiMakeDiaryNote
n  'w'i          <Plug>VimwikiDiaryGenerateLinks
n  'wi           <Plug>VimwikiDiaryIndex
n  'ws           <Plug>VimwikiUISelect
n  'wt           <Plug>VimwikiTabIndex
n  'ww           <Plug>VimwikiIndex
n  'bd         * :Bclose<CR>
n  'bv         & :BufExplorerVerticalSplit<CR>
n  'bs         & :BufExplorerHorizontalSplit<CR>
n  'bt         & :ToggleBufExplorer<CR>
n  'be         & :BufExplorer<CR>
n  'M          * :call magit#show_magit('v')<CR>
n  'mp           <Plug>MarkdownPreviewToggle <Space>
n  'nm           <Plug>MarkdownPreviewStop   <Space>
n  'mk           <Plug>MarkdownPreview       <Space>
n  'tk           <C-W>t<C-W>K
n  'th           <C-W>t<C-W>H
   's            :source ~/.vimrc<CR>
   'e            :e! ~/.vimrc<CR>
   'w            :w!<CR>
   'q            :e ~/buffer<CR>
   'tt           :vert term<CR>
```
