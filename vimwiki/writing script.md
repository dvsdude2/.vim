##writing keybinding script##

- in the place where you want the script to grab the keybinding info from
- add a comment eg."START_KEYS" where you want the script to start to grab lines and 
- "END_KEYS" where you want it to stop.
- $ sed -n '/START_KEYS/,/END_KEYS/p'(p for print)then the path to the source file.
- since we dont want comments or headers we can clean it up by piping into grep
- use the sed command to tell script
- by grabbing lines that start with set of characters and not the others
- in this example comments started with "--" while the keybindings started with ", ("
- $ sed -n '/START_KEYS/,/END_KEYS/p' ~/.config/examplefile.eg | grep ', ('
- since there were keybinding that were commented out they remain in the results
- in order to eliminate these he does a reverse grep. by piping into grep but with -v flag + 'pattern not wanted'
- $ sed -n '/START_KEYS/,/END_KEYS/p' ~/.config/examplefile.eg | grep ', (' | grep -v '-- , ('
- at this point in the video the command he is running throws a error. grep deosn't like the '--' pattern and he has to escape out
- to do this he seperates them with backslashes so |grep -v '\-\- , ('instead
- this is where he notice not all keybinding were being listed because the first line doesnt fit the pattern
- he moves to the first grep and adds a -e flag whitch allows him to run it a multiple times.
- adds the second pattern whitch he also has to escape out of with a backslash. so now looks like
- $ sed -n '/START_KEYS/,/END_KEYS/p' ~/.config/examplefile.eg | grep -e ', ("' -e '\[ (' | grep -v '\-\- , ("'
- up till now he has been using the command line in terminal. so now he makes a file by copying it and starting a new file
- the new script file should have the shebang and file name end in .sh. for this we'll call new_script.sh
- he then makes line breaks with the backslash so the file looks like
- #!/bin/bash
  sed -n '/START_KEYS/,/END_KEYS/p' ~/.config/examplefile.eg | \
  grep -e ', ("' \
  -e '\[ (' | \
  grep -v '\-\- , ("'
- then writes or save file opens a anouther terminal cd into directory with said file and makes it executable.
- types command $ chmod +x new_script.sh 
- since the output still has bunch of stuff not needed eg. (leading spaces,commas,quotes)
- he uses the sed command with the -e flag to run it couple times
- $ sed -e 's/^[ \t]*//' the 's/ for substatute the carrot stick for start of the line
- the brackets for what is to be replaced, the wildcard for all, the two forward slashes means replace with nothing.
- finish closing quote then line break to start next sed to remove the comma


