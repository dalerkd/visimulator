# visimulator
update 2017-12-09
Features
0: move the cursor to colum 1 (hard beg-of-line)
$: move the cursor to end-of-line
^: move the cursor to the first non-blank character (soft beg-of-line)
-: move the cursor to the first non-blank character (soft beg-of-line) of the previous [count] line
+,: move the cursor the first non-blank character (soft beg-of-line) of the next [count] line
h: move the cursor to left [count] colum
j: move the cursor to down [count] line
k: move the cursor to up [count] line
l: move the cursor to right [count] colum
w: move the cursor to the beginning of next [count] word
b: move the cursor to the beginning of previous [count] word
e: move the cursor to the end of next [count] word
ge: move the cursor to the end of previous [count] word
W: move the cursor to the beginning of next [count] WORD
B: move the cursor to the beginning of previous [count] WORD
E: move the cursor to the end of next [count] WORD
gE: move the cursor to the end of previous [count] WORD
f* ('*' can be any character): move the cursor to next [count] appearance of the character in current line (e.g. fa fb fc ...)
F*: move the cursor to previous [count] occurrence of the character in current line (e.g. Fa Fb Fc ...)
t*: move the cursor to just before the next [count] occurrence of the character in current line
T*: move the cursor to just after the previous [count] occurrence of the character in current line
;: repeat last f*/F*/t*/T* search
,: repeat last f*/F*/t*/T* search in opposite direction
H: move the cursor to the first non-blank character (soft beg-of-line) of the line at the top of the screen
M: move the cursor to the first non-blank character (soft beg-of-line) of the line at the middle of the screen
L: move the cursor to the first non-blank character (soft beg-of-line) of the line at the bottom of the screen
gg: move the cursor to the first non-blank character of the line(default the first) of the file
G: move the cursor to the last line of the file (if a count is given(e.g. 10G), move to that line)
%: move to the matching parenthesis (or similar). If a count is given(e.g. 50%), move the cursor to the line percentage of the file
*: (literal asterisk) search forward for the [count] occurrence of the word under the cursor
#: (literal hash) search backward for the [count] occurrence of the word under the cursor
Ctrl-d: Scroll file downward for half page (window)
Ctrl-u: Scroll file upward for half page (window)
Ctrl-f: Scroll file downward for one page (window)
Ctrl-b: Scroll file upward for one page (window)
z<return>: scroll the view so that current line is at the top of the screen, and move the cursor to the first non-blank character
z.: scroll the view so that current line is at the middle of the screen, and move the cursor to the first non-blank character
z-: scroll the view so that current line is at the bottom of the screen, and move the cursor to the first non-blank character
zt: scroll the view so that current line is at the top of the screen
zz: scroll the view so that current line is at the middle of the screen
zb: scroll the view so that current line is at the bottom of the screen
i[: select inner [] block, not including [ and ]. 
sample: 
'di]' or 'di[' to delete contents betwen [], 
'ci]' or 'ci[' to change contents between [], 
'yi]' or 'yi[' to copy contents between [].
i]: select inner [] block, not including [ and ]. refer to 'i['
i{: select inner {} block, not including { and }. refer to 'i['
i}: select inner {} block, not including { and }. refer to 'i['
i<: select inner <> block, not including < and >. refer to 'i['
i>: select inner <> block, not including < and >. refer to 'i['
i": select inner quotation marks "", not including ". refer to 'i['
i': select inner quotation marks '', not including '. refer to 'i['
a[: select outer [] block, including [ and ]. refer to 'i[' 
sample: 
'da]' or 'da[' to delete contents betwen [], 
'ca]' or 'ca[' to change contents between [], 
'ya]' or 'ya[' to copy contents between [].
a]: select outer [] block, including [ and ]. refer to 'a['
a{: select outer {} block, including { and }. refer to 'a['
a}: select outer {} block, including { and }. refer to 'a['
a<: select outer <> block, including < and >. refer to 'a['
a>: select outer <> block, including < and >. refer to 'a['
a": select outer quotation marks "", including ". refer to 'a['
a': select outer quotation marks '', including ". refer to 'a['
i: enter input mode to insert text before the cursor
a: enter input mode to append text after the cursor
gi: enter input mode where insert mode was exited last time
I: enter input mode before the first non-blank in the line (soft beginning-of-line)
gI: enter input mode at the column one (hard beginning-of-line)
A: enter input mode to append text after end of line
R: enter input mode in overtype mode
o: insert an new line below the cursor and enter input mode at column 1 of the new line
O: insert an new line above the cursor and enter input mode at column 1 of the new line
s: delete [count] character start from that under the cursor and enter input mode there
S: delete [count] line down from the current line (include current line), and reserve one blank line, then enter input mode at column 1 of this blank line.
C: remove all characters from the cursor to end-of-line and enter input mode there
x: delete [count] character start from the one under the cursor, and copy them to the clipboard
X: delete [count] character before the cursor, and copy them to the clipboard
~: toggle case to upper or lower of current character
r*: (where '*' is any character), replace [count] character that starts from the one under the cursor with the given character
J: join the current line with the next one, leaving exactly one space charactr between them
u: undo last action
Ctrl-r: redo last undone action
D: remove all characters start from that under the cursor to end-of-line
Y: copy current line
p: paste text in the clipboard after the cursor
P: paste text in the clipboard at the cursor
v: enter visual mode
V: enter visual mode linewise
Ctrl-e: scroll the view one line upward (keep cursor on screen)
Ctrl-y: scroll the view one line downward (keep cursor on screen)
ZZ: save current file and close it (same as :wq)
.: repeat last command
d{w|b|B|e|0|$||}{[t|T|f|F]*}: (where, '*' is any character) delete the specified region, and copy them to the clipboard
c{w|b|B|e|0|$||}{[t|T|f|F]*}: (where, '*' is any character) delete the specified region, and copy them to the clipboard, then enter input mode
y{w|b|B|e|0|$||}{[t|T|f|F]*}: (where, '*' is any character) copy the specified region to the clipboard
gu{w|b|B|e|0|$||}{[t|T|f|F]*}: (where, '*' is any character) change the characters in specified region to lower case.
gU{w|b|B|e|0|$||}{[t|T|f|F]*}: (where, '*' is any character) change the characters in specified region to upper case.
>{gg|G}: Indent all the lines from start/end/count line of the file to current line.
<{gg|G}: Unindent all the lines from start/end/count line of the file to current line.
>>: indent all the lines in the specified region
<<:unindent all the lines in the specified region
:w : save current file
:q : close current file
:wq : save and close current file
:bd : close current file
