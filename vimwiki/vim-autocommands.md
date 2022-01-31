
# Autocommands
--------------

## Basics
https://dev.to/phantas0s/a-vim-guide-for-expert-users-137b
Autocommands can automatically run a command
when a specific event happens.
it adds a command to a list of commands linked to a precise event.
When this event is fired,
every command of the list of commands are executed.

An event can be
opening Vim, reading any file, or writing a markdown file for example.

Here are the basics to manipulate autocommands:

:autocmd `<event> <pattern> <cmd>` or :au `<event> <pattern> <cmd>`
Add the command `<cmd>`
to the list of commands executed automatically when
the event `<event>` is fired.
The pattern `<pattern>`
filter the files where the autocommand should be applied.

`:autocmd <event> or :au <event>`
- Output the list of commands executed when the `<event>` is fired.

`:autocmd! <event> or :au! <event>`
- Delete the list of autocommands of the event <event>.

To clarify all this jargon, here are some examples:

`:autocmd BufWrite * echom "Write..."`
- Output "Write" each time any file is saved.
The wildcard * means "every file".

`:autocmd BufNew *.md echom "Read..."`
- Output "Read" each time a new markdown buffer is created.
Unsurprisingly, The pattern *.md means every file ending with .md.
After running these commands,
you can try to write a file (command :w) to see if it works.
If you don't see the message in the command-line,
run :messages to display them.

Multiple Events and Patterns
You can also create an autocommand with more than one event or pattern, separated with a comma. For example:

:autocmd BufNew,BufWrite *.md,*.js,*.php echom "Create or write md, js, or php..."

The command echom "Create or write md, js or php..." will run when a markdown, JavaScript, or PHP buffer is created (BufNew) or saved (BufWrite).

Note that the pattern can be a bit different depending on the events you listen to. For a description of all events available, see :help autocommand-events.

Finally, if you want the scope of the autocmd to be limited to the current buffer, you can use the special pattern <buffer>.


Autocommand Groups
Why Using Autocommand Groups?
As the name indicates, an autocommand group is a group of one or more autocommands. When you create an autocommand as we did above, it's added automatically to a default autocommand group without a name. You can create autocommand groups with names and add autocommands to it, too. You can think of it as namespaces for autocommands.

To understand this concept, let's see where it's useful to use autocommand groups. As we saw, each time you create an autocommand, it's added to the list of command triggered when a specific event occurs; even if this command is already part of the list.

Let's look at an example. First, let's add this autocommand to your vimrc:
autocmd BufWritePre * echom "Write..."
You can then try the following:

Source your virmc twice (by running :source $MYVIMRC twice).
Run :autocmd BufWrite.
This last command will output the list of commands executed when the event BufWrite is triggered. It will output something like this:
BufWritePre
    *         echom "Write..."
              echom "Write..."
The command echom "Write..." appears two times in the command list for the pattern *. As a result, each time the event occurs on any file, the command will run two times.

More often than not, we want to add our commands to the command list only once. Otherwise, it will impact performances each time the event is fired and, if the command is not idempotent, nasty bugs will pop up.

Using autocommand groups can solve this problem. Here are the basic commands you can use to manipulate these groups:

:augroup - Output all autocommand groups.
:augroup <name> or aug <name> - Call a new autocommand group named <name>. All autocommands created after this command will be part of the group.
:augroup! <name> or aug! <name> - Delete the group named <name>.
:augroup END - End the autocommand group. If you define an autocommand after this one, it won't be part of the group.
As always, here's an example:
:augroup messages
:autocmd BufWrite * echom "Write..."
:augroup END
The autocmd is now part of the autocommand group messages.

By itself, it doesn't solve our problem. If you add the three lines above in your vimrc and source multiple times, the autocommand in the group messages will be added to the autocommand list each time.

We saw above that you can delete autocommands with the command au! <event>. This will work if the autocommand is not in a named group. If you run au! BufWrite for example, it will delete every autocommand in the nameless autocommand group (the default one), but not the one in the group messages we've created above.

To solve our problem, we could delete every autocommand belonging to the group messages after creating the group itself:
:augroup messages
:au! messages
:autocmd BufWrite * echom "Write..."
:augroup END
If these lines are in your vimrc and you source it three times, every autocommand will be deleted from the group messages each time, before being added again. In short, our problem is solved: the command echom "Write..." will always appear once and only once in our list of command.

When we use au! between the initialization of the group (augroup messages) and the end of the initialization (augroup END), we don't have to indicate the name of the group. Vim will understand, in that case, that we want to delete every autocommand of the group declared just before. In short, the following commands are equivalent to the ones above:
:augroup messages
:au!
:autocmd BufWrite * echom "Write..."
:augroup END
Redeclaring an autocommand group won't recreate it, but it will add autocommands in the existing group instead. For example, you can do something like that:
augroup vimrc
au!
augroup END

augroup vimrc
    autocmd BufWrite * echom "Write..."
augroup END
Two things happen here:

A group vimrc is declared.
Autocommands are declared and added to the group vimrc.
In short, every autocommand added to the group vimrc is merged with the command :au!. You can even do better: when you create an autocommand, you can add it to an existing group directly. To do that, you can indicate the name of the group just between the command autocmd and the event name as follows:
augroup vimrc
au!
augroup END

autocmd vimrc BufWrite * echom "Write..."
You're now able to reload your vimrc as much as you want, your autocommands will only appear once in the autocommand list. It applies for other sourced files too, like the ones you might have in your folder ftplugin for example.

Ignoring Events
If you want to run a command without firing any event, you can use the command :noautocmd. To take our previous example, if you want to ignore the event BufWrite when running the command :w, you can run the following:
:noautocmd w
Vim Help
:help autocmd
:help autocommand-events
:help autocmd-events-abc
