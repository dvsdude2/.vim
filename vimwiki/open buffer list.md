
```
# bufexplorer

BufExplorer Plugin for Vim
----------------------------

====================================================================
USAGE

To start exploring in the current window, use: >
 <`Leader`>`be`   or   :BufExplorer   or   Your  key mapping

To toggle bufexplorer on or off in the current window, use: >
 <`Leader`>`bt`   or   :ToggleBufExplorer   or   Your  key mapping

To start exploring in a newly split horizontal window, use: >
 <`Leader`>`bs`  or :BufExplorerHorizontalSplit or :Your key mapping

To start exploring in a newly split vertical window, use: >
 <`Leader`>`bv`   or   :BufExplorerVerticalSplit or Your key mapping

Commands to use once exploring:

F1        Toggle help information.
enter     Opens the buffer that is under the cursor into the current
          window.
L-mouse   Opens the buffer that is under the cursor into the current
          window.
S-enter   Opens the buffer that is under the cursor in another tab.
a         Toggles whether you are taken to the active window when
          selecting a buffer or not.
b         Fast buffer switching with b<any bufnum>.
B         Works in association with the |ShowTabBuffer| option.  If
          |ShowTabBuffer| is set to 1, this toggles if BufExplorer is to
          only store the most recent tab for this buffer or not.
d         |:delete| the buffer under the cursor from the list.  The
          buffer's 'buflisted' is cleared. This allows for the buffer to
          be displayed again using the 'show unlisted' command.
D         |:wipeout| the buffer under the cursor from the list.
          When a buffer is wiped, it will not be shown
          when unlisted buffers are displayed.
F         Open selected buffer in another window above the current.
f         Open selected buffer in another window below the current.
o         Opens the buffer that is under the cursor into the current
          window.
p         Toggles the showing of a split filename/pathname.
q         Exit/Close bufexplorer.
r         Reverses the order the buffers are listed in.
R         Toggles relative path/absolute path.
s         Cycle thru how the buffers are listed.
          Either by buffer number, file name, file extension, 
          most recently used (MRU), or full path.
S         Cycle thru how the buffers are listed, in reverse order.
          Either by buffer number, file name, file extension, most
          recently used (MRU), or full path.
t         Opens the buffer that is under the cursor in another tab.
T         Toggles to show only buffers for this tab or not.
u         Toggles the showing of "unlisted" buffers.
V         Open the selected buffer in another window on the left of the current.
v         Open the selected buffer in another window on the right of the current.

Once invoked, Buffer Explorer displays a sorted list (MRU is the default
sort method) of all the buffers that are currently opened. You are then
able to move the cursor to the line containing the buffer's name you are
wanting to act upon. Once you have selected the buffer you would like,
you can then either open it, close it (delete), resort the list, reverse
the sort, quit exploring and so on...
With bufexplorer, you can quickly and easily switch between buffers 
by using the one of the default public interfaces:

\<Leader\>be normal open

\<Leader\>bt toggle open / close

\<Leader\>bs force horizontal split open

\<Leader\>bv force vertical split open

Once the bufexplorer window is open you can use the normal movement keys (hjkl) to move around and then use or to select the buffer you would like to open. If you would like to have the selected buffer opened in a new tab, simply press either or 't'. Please note that when opening a buffer in a tab, that if the buffer is already in another tab, bufexplorer can switch to that tab automatically for you if you would like. More about that in the supplied VIM help.

Bufexplorer also offers various options including:

    Display the list of buffers in various sort orders including:
        Most Recently Used (MRU) which is the default
        Buffer number
        File name
        File extension
        Full file path name
    Delete buffer from list

For more about options, sort orders, configuration options, etc. please see the supplied VIM help.
vim.org

This plugin can also be found at http://www.vim.org/scripts/script.php?script_id=42.
```
