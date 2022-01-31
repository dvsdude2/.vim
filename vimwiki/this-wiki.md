
[vim diary](vim diary help) diary


`*UPDATE*`super d brings up diary with todays date.
-----------------------------------------
   * With a little more looking I believe the way it is suppose to work.
    *- first you have to open vim 
    *- then type in `Leader`-`w`,`leader`-`w`
    *- this opens a diary page named todays date
- after making the note you write it. and close at witch point you
head over to the index page with `leader`-`wi` which opens the index
- while there you type in `leader`-`w`, `leader`-`i` and it'll place
 a link to that note you made earlier.




MAP                MODE
                       *vimwiki_<Leader>wh*
<Leader>wh         n   Convert current wiki page to HTML.
                       Maps to |:Vimwiki2HTML|
                       Remap command: `<Plug>Vimwiki2HTML`

                      *vimwiki_<Leader>whh*
<Leader>whh        n   Convert current wiki page to HTML
                       and open it in the webbrowser.
                       Maps to |:Vimwiki2HTMLBrowse|
                       Remap command: `<Plug>Vimwiki2HTMLBrowse`

                       *vimwiki_<Leader>w<Leader>i*
<Leader>w<Leader>i n   Update diary section (delete old, insert new)
                       Only works from the diary index.
                       Maps to |:VimwikiDiaryGenerateLinks|
                       Remap command: `<Plug>VimwikiDiaryGenerateLinks`

                       *vimwiki_<CR>*
<CR>               n   Follow/create wiki link
                       (create target wiki page if needed).
                       Maps to |:VimwikiFollowLink|.
                       Remap command: `<Plug>VimwikiFollowLink`

                       *vimwiki_<S-CR>*
<S-CR>             n   Split and follow 
                       (create target wiki page if needed).
                       May not work in some terminals.
                       Remapping could help.
                       Maps to |:VimwikiSplitLink|.
                       Remap command: `<Plug>VimwikiSplitLink`

                       *vimwiki_<C-CR>*
<C-CR>             n   Vertical split and follow
                       (create target wiki page if needed). 
                       May not work in some terminals. Remapping
                       could help.
                       Maps to |:VimwikiVSplitLink|.
                       Remap command: `<Plug>VimwikiVSplitLink`

                       *vimwiki_<C-S-CR>*    *vimwiki_<D-CR>*
<C-S-CR>, <D-CR>   n   Follow wiki link (create target wiki page if needed),
                       opening in a new tab.
                       May not work in some terminals. Remapping could help.
                       Maps to |:VimwikiTabnewLink|.
                       Remap command: `<Plug>VimwikiTabnewLink`

                       *vimwiki_<Backspace>*
<Backspace>        n   Go back to previously visited wiki page.
                       Maps to |:VimwikiGoBackLink|.
                       Remap command: `<Plug>VimwikiGoBackLink`

                       *vimwiki_<Tab>*
<Tab>              n   Find next link in the current page.
                       Maps to |:VimwikiNextLink|.
                       Remap command: `<Plug>VimwikiNextLink`

                       *vimwiki_<S-Tab>*
<S-Tab>            n   Find previous link in the current page.
                       Maps to |:VimwikiPrevLink|.
                       Remap command: `<Plug>VimwikiPrevLink`

                       *vimwiki_<Leader>wn*
<Leader>wn         n   Goto or create new wiki page.
                       Maps to |:VimwikiGoto|.
                       Remap command: `<Plug>VimwikiGoto`

                       *vimwiki_<Leader>wd*
<Leader>wd         n   Delete wiki page you are in.
                       Maps to |:VimwikiDeleteFile|.
                       Remap command: `<Plug>VimwikiDeleteFile`

                       *vimwiki_<Leader>wr*
<Leader>wr         n   Rename wiki page you are in.
                       Maps to |:VimwikiRenameFile|.
                       Remap command: `<Plug>VimwikiRenameFile`

