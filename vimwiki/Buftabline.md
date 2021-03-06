```
# buftabline
------------


*buftabline.txt* Use the tabline to render buffer tabs

		BUFTABLINE  by Aristotle Pagaltzis

====================================================================
0. Contents                                     *buftabline*

1. Intro .......................................buftabline-intro
2. Configuration settings ......................buftabline-config
3. Mappings ....................................buftabline-mappings
4. Tab coloring and colorscheme support ........buftabline-colors
5. Source ......................................buftabline-source


====================================================================
1. Intro                                  *buftabline-intro*

This plugin takes over the 'tabline' and renders the buffer list
in it instead of a tab list. 
It is designed with the ideal that it should Just Work:
drop it into your setup and you're done. 
There is only minimal configurable behavior.


====================================================================
2. Configuration settings                     *buftabline-config*

Changes to any of the plugin's configuration settings at runtime 
will not take effect immediately unless you force an update: >
    :call buftabline#update(0)
<

*g:buftabline_show*          number (default 2)

The value of this option specifies when the line with buffer labels 
will be displayed:
         0: never
         1: only if there are at least two buffers
         2: always
This is analogous to the 'showtabline' setting,
only for the |buftabline|.


*g:buftabline_numbers*       number (default 0)

The value of this option specifies how to number the buffer labels:
         0: no numbering
         1: buffer number
         2: ordinal number
The buffer number corresponds to Vim's internal buffer number
as shown by the |:ls| command, whereas the ordinal number is a
simple sequential count from left to right.


*g:buftabline_indicators*    boolean (default off)

When on, the buffer's state is indicated in the buffer label.
Currently the only state indicated is 
whether the buffer is 'modified'.


*g:buftabline_separators*    boolean (default off)

When on, a vertical line is drawn inbetween tabs.
(This is not strictly correct. 
The effect is actually achieved by replacing the space on the
left side of each tab with U+23B8 LEFT VERTICAL BOX LINE.
Therefore the separator will be highlighted the same way
as the tab to its left.)


*g:buftabline_plug_max*      number (default 10)

The number of |buftabline-mappings| that will be created
by the plugin.  You can request more of them or turn off
the functionality entirely by setting this to 0.
Note it only has an effect before loading the plugin,
not if you change it later.


====================================================================
3. Mappings                                 *buftabline-mappings*

To switch buffers by their ordinal number
(|g:buftabline_numbers| = 2) you can map keys to the
|<Plug>| mappings provided by this plugin: >
        nmap <leader>1 <Plug>BufTabLine.Go(1)
        nmap <leader>2 <Plug>BufTabLine.Go(2)
        nmap <leader>3 <Plug>BufTabLine.Go(3)
        nmap <leader>4 <Plug>BufTabLine.Go(4)
        nmap <leader>5 <Plug>BufTabLine.Go(5)
        nmap <leader>6 <Plug>BufTabLine.Go(6)
        nmap <leader>7 <Plug>BufTabLine.Go(7)
        nmap <leader>8 <Plug>BufTabLine.Go(8)
        nmap <leader>9 <Plug>BufTabLine.Go(9)
        nmap <leader>0 <Plug>BufTabLine.Go(10)
<
There is also a |<Plug>| mapping 
which always switches to the last buffer: >
        nmap <leader>0 <Plug>BufTabLine.Go(-1)

====================================================================
4. Tab coloring and colorscheme support       *buftabline-colors*

This plugin uses several custom highlight groups
to render the buffer tabs.
The custom groups are linked to several other
built-in Vim highlight groups that should provide a sensible default
which automatically harmonizes with your |colorscheme|.

However, if you dislike your colorscheme's chosen tabline colours,
you can override the default links in your vimrc -- c.f. |:hi-link|.


The highlight groups and their default links are as follows:

Custom group                 Default link         Meaning
BufTabLineCurrent            |TabLineSel|           Buffer shown in current window
BufTabLineActive             |PmenuSel|             Buffer shown in other window
BufTabLineHidden             |TabLine|              Buffer not currently visible
BufTabLineFill               |TabLineFill|          Empty area
BufTabLineModifiedCurrent    |BufTabLineCurrent|    (Same as linked but 'modified')
BufTabLineModifiedActive     |BufTabLineActive|     (Same as linked but 'modified')
BufTabLineModifiedHidden     |BufTabLineHidden|     (Same as linked but 'modified')
```



