```



i  <S-Tab>     *@vimwiki#tbl#kbd_shift_tab()
i  <S-CR>      *@<Esc>:VimwikiReturn 2 2<CR>
i  <C-L><C-M>   @<Plug>VimwikiListToggle
i  <C-L><C-K>   @<Plug>VimwikiListPrevSymbol
i  <C-L><C-J>   @<Plug>VimwikiListNextSymbol
i  <C-T>        @<Plug>VimwikiIncreaseLvlSingleItem
i  <C-D>        @<Plug>VimwikiDecreaseLvlSingleItem
i  <Plug>VimwikiListToggle &@<Esc>:VimwikiListToggle<CR>
i  <Plug>VimwikiListPrevSymbol &@<C-O>:VimwikiListChangeSymbolI prev<CR>
i  <Plug>VimwikiListNextSymbol &@<C-O>:VimwikiListChangeSymbolI next<CR>
i  <Plug>VimwikiIncreaseLvlSingleItem &@<C-O>:VimwikiListChangeLvl increase 0<CR>
i  <Plug>VimwikiDecreaseLvlSingleItem &@<C-O>:VimwikiListChangeLvl decrease 0<CR>
i  <Plug>MarkdownPreviewToggle *@<Esc>:MarkdownPreviewToggle<CR>
i  <Plug>MarkdownPreviewStop *@<Esc>:MarkdownPreviewStop<CR>a
i  <Plug>MarkdownPreview *@<Esc>:MarkdownPreview<CR>a
i  <CR>        *@<C-]><Esc>:VimwikiReturn 1 5<CR>
i  <Plug>CocRefresh * <C-R>=coc#_complete()<CR>
i  <S-Tab>       <Plug>SuperTabBackward
i  <Plug>SuperTabBackward & <C-R>=SuperTab('p')<CR>
i  <Plug>SuperTabForward & <C-R>=SuperTab('n')<CR>
i  <C-X>       * <C-R>=<SNR>17_ManualCompletionEnter()<CR>
i  <C-Tab>     * <Tab>
i  <F4>        * <C-R>=strftime("%c")<CR>
i  <Tab>         <Plug>SuperTabForward
i  <CR>        * pumvisible() ? coc#_select_confirm() : "\<C-G>u\<CR>"
i  jh          * <Esc>

```
