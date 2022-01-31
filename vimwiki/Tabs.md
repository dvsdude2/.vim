```
TAB VIEWS
:tabe filename      -   opens the file in newtab
:tabe new           -   open an empty tab
:tabs               -   list opened tabs
:tabc               -   close the active tab
:tabn and tabp      -   Go to next tab or previous tab
:tabfirst           -   Go to the first available tab
:tablast            -   Go to the last available tab
:help tabpage       -   help for tabs

vim -p *.txt        -   open all txt files in tabs
TAB NAVIGATION
gt                  -   go to next tab
gT                  -   go to previous tab
{i}gt               -   go to tab in position i
TAB SHORTCUTS
CTRL+W T            -   Break out current window into a new tabview
CTRL+W o            -   Close every window in the current tabview but the current one
CTRL+W n            -   create a new window in the current tabview
CTRL+W c            -   Close current window in the current tabview



" open tabs with Leader-<tab number>
map <Leader>1 :tabn 1<CR>
map <Leader>2 :tabn 2<CR>
map <Leader>3 :tabn 3<CR>
map <Leader>4 :tabn 4<CR>
map <Leader>5 :tabn 5<CR>
```
