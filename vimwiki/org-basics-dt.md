```
#+TITLE:org-mode basics in doom emacs
#+Discription: An org document to demonstrate org mode.
#+Author: Me, Myself, and I

-*- org mode basics -*-
* A New Headline
** level2
*** level3
**** level4
***** level5
* Getting Started In Org Mode
Read org mode manual with M-x org-info
** org-toggle-heading : SPC-m-h
- org-toggle-item : SPC-m-i
- Unordered list item one
- Unordered list item two
  - You can use dash instead of +
  - Another list item.
    1. Ordered list item one.
    2. Ordered list item two.
* A new headline
** Level 2
*** Level 3
**** Level 4
***** Level 5
****** Level 6
** Rotate current subtree between states: TAB
** Rotate entire buffer between states : S-TAB
** close (fold) the tree : zc
** open (unfold) the tree : zo
** fold everything : zM
** unfold everything : zR
* Motion
** move left/down/up/right : h/j/k/l
** next/prev heading : gj/gk OR CTR-j/k
** move parent/child element : gh/gl
* Structure Editing
** insert new heading/item at current level : M-RET
** insert new heading after subtree : C-RET
** promote/demote heading : M-h/l  OR  M-LEFT/RIGHT
** promote/demote current subtree : M-S-h/l  OR  M-S-LEFT/RIGHT
** move subtree/list item up/down : M-j/k
** move list item up/down but not subtree : M-S-j/k
* Some advanced editing thanks to Evil Mode!
** select an element : vae
** delete an element : dae
** select a subtree : vaR
** delete subtree : daR
** yank subtree : yiR
* Insert Snippets
** SPACE-i-s
** bang : #!/usr/bin/env bash
** Insert a license : pick a free license
** current time  : Sun Feb  9 20:06:29 2020
** pi :
# -*- mode: snippet -*-
3.141592654
* TODO Set TAGS with : SPC-m-q :TODO:
** TODO example one
** TODO example two : S-RIGHT
** To remove TODO : S-LEFT
** toggle the todo state : SPC-m-t
** org-schedule : SPC-m-s
SCHEDULED: <2020-02-10 Mon 14:00-15:30>
** [#A] org-priority : SPC-m-p
** To create checkbox : - [ ]  [1/3] [33%]
DEADLINE: <2020-02-22 Sat 01:00-03:00>
- [ ] eggs
- [ ] milk
- [X] beer : C-c C-c OR RET
** Move this file to front of agenda : C-c-[
** Org-agenda : SPC-o-a
** Tag search : SPC-o-a-m
* Tables
** Creating a table
*** just start typing, e.g.|Name|Phone|Age RET |- TAB
*** convert region to table : C-c |
*** Go to forward/backward by cell : TAB/S-TAB
*** ...  separator at least 3 spaces : C-3 C-c |
*** Make org table headline : SPC m b -
*** Duplicate a field in the cell below : S-RET
| ONE                | TWO        | THREE | FOUR     |
|--------------------+------------+-------+----------|
| This is a sentence | Some stuff | More  | ffffffff |
| This is a sentence | Some stuff |       |          |
|                    | Some stuff |       |          |
*** Move current row UP : M-k
*** Move current row DOWN : M-j
*** Move current column LEFT : M-h
*** Move current column RIGHT : M-l
*** Insert new column : M-S-l
*** Delete current column : M-S-h
*** Insert new row : M-S-j
*** Delete current row : M-S-k
** Commands available inside tables
The following commands work when the cursor isinside a table.
Outside of tables, the same keys may have other functionality.
```
