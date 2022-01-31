```
Use <cr> to confirm completion
Use <Tab> or custom key for trigger completion
Use <Tab> and <S-Tab> to navigate the completion list:
    - [x] inoremap <expr> <Tab> pumvisible() ? "\<C-n>" : "\<Tab>"
    - [x] inoremap <expr> <S-Tab> pumvisible() ? "\<C-p>" : "\<S-Tab>"
* note there is a new one that seems to work and is from their documentation.
*    
" use tab to make selections ...was taken down for debugging
inoremap <silent><expr> <Tab>
      \ pumvisible() ? "\<C-n>" :
      \ <SID>check_back_space() ? "\<Tab>" :
      \ coc#refresh()
      
not 100% sure about this plugin.....maybe overkill for my needs
there may well of been a native completion that enough for my needs????
checking into but it is working and it had to be abit of a bear to install
there for i'm reluctant to remove it. may check another version that does not
have it already installed.
```
