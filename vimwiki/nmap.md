```
==== nmap (all) ====
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
n  /           * q/i
n  :           * q:i
   H           * ^
   L           * $
n  Q           * :Bclose<CR>
n  [e          * :<C-U>execute 'move -1-'. v:count1<CR>
n  [<Space>    * :<C-U>put! =repeat(nr2char(10), v:count1)<CR>'[
   \`            i`<Esc>ea`<Esc>
n  ]e          * :<C-U>execute 'move +'. v:count1<CR>
n  ]<Space>    * :<C-U>put =repeat(nr2char(10), v:count1)<CR>
n  gx            <Plug>NetrwBrowseX
n  gcu           <Plug>Commentary<Plug>Commentary
n  gcc           <Plug>CommentaryLine
n  gc            <Plug>Commentary
n  j           * gj
n  k           * gk
   <C-N>         :NERDTreeToggle<CR>
   <C-Down>    * :resize -3<CR>
   <C-Up>      * :resize +3<CR>
   <C-Right>   * :vertical resize -3<CR>
   <C-Left>    * :vertical resize +3<CR>
n  <C-L>       * <C-W>l          <Space>
n  <C-K>       * <C-W>k          <Space>
n  <C-J>       * <C-W>j          <Space>
n  <C-H>       * <C-W>h          <Space>
   <C-S-Down>  * YP
   <C-S-Up>    * YP
   <Down>      * gj
   <Up>        * gk
```
