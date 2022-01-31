
#+TITLE:Org Take Notes
#+Discription : trying to make org mode work for me.



* How do you take notes in Org?
-----------------------------

Are you buried in a heap of uncategorized notes?
Do you manually open the right file & navigate to the right heading?
Are you mystified by org-capture and org-refile?
Here's a path that can help you
learn how to more efficiently take and organize! notes in Org Mode.

Set up a keyboard shortcut to go to your main Org file
Use org-refile to file or jump to headings
Use org-capture to write notes quickly
Define your own org-capture templates for greater convenience
Pull in additional information

* Step 1. Set up a keyboard shortcut to go to your main Org file
---------------------------------------------------------------

Instead of using `SPC-.` (find-file) all the time,
set up shortcuts to jump to the Org files you use the most.
This way, you can easily type that keyboard shortcut,
go to the end of the file, and add your note.
Here's some sample code
that sets the C-c o shortcut to open organizer.org
in your home directory. You can add it to your ~/.emacs.d/init.el  ~
and then call M-x eval-buffer to load the changes.

```Lisp 
(global-set-key (kbd "C-c o")
                (lambda () (interactive) (find-file "~/organizer.org")))
```

Once you're in your Org file, you can use `M->` (end-of-buffer)
to go to the end of the file,
or you can use `C-s` (isearch-forward) to search for some text.

You'll still need to switch back to your original buffer
or window configuration when you're done,
but that's something you can fix when you learn how to use
[org capture](SPC-x).

* Step 2. Use org-refile to file or jump to headings
--------------------------------------------------

The next improvement is
to use [org refile]() to move the current subtree to a specific heading,
or jump to one without moving any text.
This will let you quickly go to a project from anywhere in Org Mode.

By default, org-refile will show you only the top-level headings
of the current file. Let's configure it to show you headings
from all your agenda files. You can use M-x customize-variable
to change org-refile-targets. Click on the INS button,
then click on Value menu next to Identify target headline by.
Change this to Max level number. In the Integer
field, fill in a suitably high number, like 6.
This is the maximum depth of headings that will be shown.

If you prefer to set your variables using Emacs Lisp,
here's the code that you can add it to your init.el.
Call M-x eval-buffer to load the changes.
```
(setq org-refile-targets '((org-agenda-files . (:maxlevel . 6))))
```
Be sure to add your main Org Mode file to your agenda list.
You can do so by going to the file and typing
C-c [ (org-agenda-file-to-front),
or by setting the org-agenda-files variable.

The standard Emacs completion interface
isn't as friendly as it could be.
I use the Helm package to make it easier to select and complete input.
Since Helm can be a little complex,
you may want to start with ido-mode instead.
Here's how you can set Ido up to use with Org Mode:

`(ido-mode)`
`(setq org-completion-use-ido t)`

Once you've set up your org-refile-targets, your agenda files,
and either Helm or Ido, you can get the hang of using org-refile.
The standard keyboard shortcut for org-refile is
`C-c C-w` when you're in an Org Mode buffer.
org-refile can do different things depending on how you call it:
By default, it moves the current subtree to the specified location.
If you call it with the prefix argument C-u (like so:
`C-u C-c C-w`,
it jumps to the specified location instead of moving the current subtree.
If you call it as
`C-u C-u C-c C-w`,
it jumps to the previous refiling location.
First, practise using it with the prefix argument
`C-u C-c C-w` to jump to a location.
Once you've gotten the hang of that,
go to some of your uncategorized entries and use org-refile
without the prefix argument
`C-c C-w` to move the entries to the right place.

org-refile gives you a quick way to jump to a heading,
but you still have to find your way back to whatever
you were working on before you wanted to take a note.
After you're comfortable with refiling notes to the right place,
move on to learning how to use
[org capture]() to quickly take notes from anywhere.

Step 3. Use org-capture to write notes quickly
----------------------------------------------

org-capture can help you take notes quickly by popping up a window
or leading you through prompts. When you're done taking the note,
it will return you to whatever you were looking at
before you started. In order to take advantage of this, though,
you'll need to customize org-capture.

The Org Mode manual
recommends giving org-capture a global keyboard shortcut such as
C-c c In Doom emacs this is set to 
`SPC x`

This is not needed in Doom Emacs
(global-set-key (kbd "C-c c") 'org-capture)

You can use M-x customize-variable
to set org-default-notes-file
to the filename you would like notes to be saved to,
or set it in Emacs Lisp code like this:

(setq org-default-notes-file "~/organizer.org")
Make sure that the file exists and is automatically opened in Org Mode.

If you type`SPC x`
org-capture will display a prompt.
`t` is a simple task template, and
`C` will show you the customization interface for org-capture-templates.

Let's start with `t`.
It will show you a buffer with a simple TODO entry.
You can fill in the rest of the details,

use C-c C-s (org-schedule) to schedule it for a particular day,
set the deadline with C-c C-d (org-deadline), etc.
You can change the TODO keyword or delete it.

When you're done, type
C-c C-c to automatically save it to your default notes file
(as specified by org-default-notes-file). Changed your mind?
Cancel with C-c C-k.
After either C-c C-c or C-c C-k,
you should be back to whatever it was that you were working on.

Practise using `SPC x`  (org-capture) 
to quickly jot down several tasks or notes.
Then go to your notes file
and use `C-c C-w` (org-refile)
to move the notes to the right place.

You can also refile the notes right from the capture buffer.
Instead of typing C-c C-c to finish your note,
use C-c C-w to refile it.

Get the hang of using org-capture to take notes,
organizing them every so often
(maybe at the end of your day, or once a week?)
or refiling them as you go.

Step 4. Define your own org-capture-templates for greater convenience
If you find yourself capturing different kinds of notes often
or you want to capture in another format (table entry? list item?)
invest the time in customizing org-capture-templates.
In the beginning,
you might find the Customize interface you get from
M-x customize-variable org-capture-templates
to be easier to work with than setting the values in
Emacs Lisp since the Customize interface lists the options.
Read the documentation and look at examples of how other people
have configured their org-capture-templates for more ideas.
I have quite a few templates defined in my config
and http://doc.norang.ca/org-mode.html has a number of templates too.

Step 5. Pull in additional information
org-capture and org-refile are great when you're at your computer
but what if you're away?
Quite a few people use MobileOrg to take quick notes on the go.
I haven't gotten around to setting that up for my workflow properly
instead, I use Evernote to jot quick notes on my phone.
As part of my weekly review process
look at the notes in my Evernote inbox
and copy them into Emacs as needed.

You can manually copy information
from your preferred non-Emacs note-taking tools
or you can figure out an automatic way of doing so.
For example, I have some code to copy Evernote notes
titled "Journal" into an Org Mode file structured by year-month-day.

Tweak your workflow!
Here's a quick sketch showing some of your workflow options
when it comes to capturing and organizing information with Org Mode.
Which combination do you prefer
and how could you make it even better?

