
# surround.vim made me love Vim
## [web-link](https://towardsdatascience.com/how-i-learned-to-enjoy-vim-e310e53e8d56)
_____________________________________________

### Surround.vim

The surround.vim plugin
lets you deal with pairs of things surrounding things,
like brackets, HTML tags, and quotation marks.
Whether you’re coding or writing,
this plugin can make your life much easier.


Learning and Deliberate Practice Tips
First,
understand how the plugin works
learn how to surround (ys), delete (ds), and change (cs).
Then, work through guided examples, like the ones below.
Once you understand the basics,
immediately start using the plugin in your everyday writing/coding.
To improve rapidly,
use deliberate practice: Every day,
identify your weak areas (e.g., adding quotes multiple words),
work through relevant guided examples
(see Surround Multiple Words section below),
generate more examples yourself, and test yourself repeatedly
until you can execute the correct motions/keystrokes
without having to think too much.
If you engage in this kind of deliberate practice for a few days —
even if it’s just a few minutes each day —
you’ll become good at using surround.vim very quickly.

Surround One Word
-----------------
I am happy.
I am "happy".
Solution: `ysiw"`
ys: add surroundings;
iw: entire word,
no matter where the cursor is
as long as it's at the word
you want to surround; "
character to surround text with

Surround Entire Line
--------------------
I am happy; she is sad.
(I am happy; she is sad.)
Solution: `yss)`
ys: add surroundings;
s: entire line;
character to surround line with)
Note: If you use yss( instead of yss),
spaces will be added around your text: ( I am happy; she is sad. )
Surround Entire Line or Paragraph with Tags
Hello World! How are you?
<p>Hello World! How are you?</p>
Solution:` yss<p>`
yss: add surroundings to entire line; <p> tag to surround line with
Note: The closing tag </p> will be auto-completed. Very convenient!

Surround Multiple Words
-----------------------
I am very very happy.
I am *very very* happy.
Solution:2`ys2aw2*`
ys: add surroundings;
2: number of words to surround,
starting with the word under the cursor;
aw: around words; *: character to surround text with)
Surround Multiple Words with Tags
Hello World! How are you?
<em>Hello World</em>! How are you?
Solution: ys2aw<em>
add surroundings around 2 words;
remember to place your cursor under Hello first!

Surround Selected Text
----------------------
The solution is "x + y = z". You responded wrongly.
Solution: Place cursor under x, then `veeeeS"`
(v: enter visual mode to select text;
eeee: press however many times you need
to select the number of words you want to select;
S" surrounds the selected text with ")

Delete Surroundings
-------------------
"Hello World!"
Hello World
Solution: `ds"`
ds: delete surrounding;
": character to delete;
place cursor anywhere inside the text area
+ Delete Surrounding Tags
<em><p>Hello World!</p></em>
Hello World!
Solution: dstdst
(dst; delete surrounding tag);
if you install repeat.vim, you can use .
to repeat, so dst. will be the same as dstdst

Change Surroundings
-------------------
"Hello World!"
*Hello World!*
Solution: cs"*
cs: change surrounding;
": existing surrounding;
*: new surrounding)
+ Change Surrounding Tags
<p>Hello World!</p>
<em>Hello World!</em>
Solution: cst<em>
cst: change surrounding tag;
<em>: new surrounding

Common Example 1
----------------
Find the mean of a set of numbers
3 + 2 + 5 + 7 / 4  
* wrong because brackets are missing
solution
place cursor under 3, then `veeeeS)`
(3 + 2 + 5 + 7) / 4
* surround text with functions/methods when coding
(3 + 2 + 5 + 7) / 4  # yss)iprint
print((3 + 2 + 5 + 7) / 4)

Common Example 2
----------------
Emphasize text, with and without repeat.vim
Hello World.
Hello *World*. 
Hello **World**.
Solution 1 (without repeat.vim): ysiw*lysiw
after moving cursor to under W (ysiw*: surround word with *; l: move cursor to W again; ysiw*: surround word with *)
Solution 2 (with repeat.vim): ysiw*l. (. repeats ysiw*)
Conclusion
To help with deliberate practice, I’ve consolidated all the examples above so you can easily use them to test yourself regularly. For each example, the first row is the original/starting text and the second row is the goal or end state. Have fun and also check out the documentation!

# surround.vim practice
# Surround
I am happy.      # start
I am "happy".    # goal
I am happy; she is sad.
(I am happy; she is sad.)
Hello World! How are you?
<p>Hello World! How are you?</p>
I am very very happy.
I am *very very* happy.
Hello World! How are you?
<em>Hello World</em>! How are you?
The solution is x + y = z. You responded wrongly.
The solution is `x + y = z`. You responded wrongly.
# Delete
"Hello World!"
Hello World
<em><p>Hello World!</p></em>
Hello World!
# Change
"Hello World!"
*Hello World!*
<p>Hello World!</p>
<em>Hello World!</em>
# Examples
3 + 2 + 5 + 7 / 4
print((3 + 2 + 5 + 7) / 4)
Hello World.
Hello **World**.

