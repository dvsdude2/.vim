```
# buffers
---------

BUFFERS
:ls (or :buffers)   -   list / show available buffers
:e filename         -   Edit a file in a new buffer
:bnext (or :bn)     -   go to next buffer
:bprev (of :bp)     -   go to previous buffer
:bdelete (or :bd)   -   unload a buffer (close a file)
:bwipeout (or :bw)  -   unload a buffer and deletes it
:b [N]              -   The number of the buffer you want to open
:ball               -   opens all buffers in horizontal split window
:vertical ball      -   opens all buffers in vertical split window
:q                  -   close the buffer window
:help buffers       -   help for buffers
:r <file_path>      -   reads a file from the path to the buffer
:r !<command>       -   reads the output of the command into buffer
:.! cat <file_path> -   reads the output of the command
                        (eg: cat) into buffer or !! in ex-mode
```
