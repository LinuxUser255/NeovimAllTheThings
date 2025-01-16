# How to use this file

open it up in neovim, and just follow along
use it to practice using neovim

It's not supposed to look pretty as a rendered mark down

## Have fun!

### Change
`c` is a powerful motion.  You use it just like `d` but at the end of the
motion you are ejected from `NORMAL` and into `INSERT`.

So if you wished to delete a word and then type in a new word, `c` is a great
habit to form.

Lets see the difference

// dd this line
// cc this line

### Horizontal Movement
Lets learn about!: `_`, `0`, `$`, `D`, `C`, `S`, `f`, `,`, `;`, `t`, `F`, and `T`
`D`, `C`, and, `S` deletes a line and lands in insert mode

`f` find then type the char to find

`,`, jump back to selected char

`;`, jump forward to next selected char

`t`,

`F`,

`T`


// How would we move around on the line with "contents"
if (true) {
    contents conTenTs contenTS
}

### Vertical Movement
#### Core movement
Rely on relative jumps.  Get good at them.

If you get NeoVim, try VimBeGood

#### { and }
We know about search.  That is a vertical movement, but its really specific.

First lets talk `{` and `}`

ContiguousCode
ContiguousCode
    ContiguousCode
    ContiguousCode
        ContiguousCode
    ContiguousCode
ContiguousCode

ContiguousCode
ContiguousCode
    ContiguousCode
    ContiguousCode
        ContiguousCode
    ContiguousCode
ContiguousCode

##### Benefits?  Class chat
This next one is a bit odd

#### Ctrl+u/d
So lets do another type of navigation.

Try pressing `<C-d>`

.
.
1 ContiguousCode
2 ContiguousCode
3 ContiguousCode
4 ContiguousCode
5 ContiguousCode
6 ContiguousCode
7 ContiguousCode
 .




Copy-pasting
ContiguousCode
1. go into normal mode
2. put the cursor somewhere along the paragraph or codeblock
3. then hit leader y
this will prep the clipboard to copy text
4. then hit ap (this will select and copy the paragraph or codeblock
5. and paste it  below, or where ever you place the cursor.


.
1 ContiguousCode
2 ContiguousCode
3 ContiguousCode
4 ContiguousCode
5 ContiguousCode
6 ContiguousCode
7 ContiguousCode


8 ContiguousCode
9 ContiguousCode
10 ContiguousCode
11 ContiguousCode


.
1 ContiguousCode
2 ContiguousCode
3 ContiguousCode
4 ContiguousCode
5 ContiguousCode
6 ContiguousCode
7 ContiguousCode
 .

.
.

.

copy the entire contents of a file in the clipboard.
noremap<leader>Y gg"yG
leader + shift +  y

.
.


##### Benefits?  Class chat

#### [m / ]m and [M / ]M
This will move by "function".  It works pretty well in c languages.

Move your cusor to this line and press `]m`.  Try moving back and forth and try
the uppercase version as well.

if (foo) {
    some content
    some content
    some content
    some content
    function bar() {
        some other content
        some other content
        some other content
        some other content
    }
    function baz() {
        other content
        other content
        other content
        other content
    }
}

##### Benefits?

#### %
Ok,.... soo this isn't a pure vertical motion.  It actually is a pair jumper

if (true) {
    content
    const a = [
        content,
        content,
        content,
    ]

    "content"

    content
    content
}

Lets combine it with a motion.  Delete the `const a =...` statement.

### Get zany...
Lets look at the following statement, what are some ways you can delete the
contents of the if statement?

if (true) {
    line1
    line2
    line3
    line4
    line5
}

I was hoping to hear `f{V%D`.  That is just so sexy. `d4j` is ok.  Relative
jump, well done..  `5dd` meh.  I would glad hand like a politician with `dd dd
dd dd dd`.  Just say mean things behind your back.

So lets try again.. but I spiced it up.

if (true) {
    line1
    // Some distance
    line2
    line3

    line4
    line5
}

First, place your cursor _in_ the if statement under the if.
Where ever you want. Then
Type `di{`

i = inside

if (true) {
    line1
    // Some distance
    line2
    line3

    line4
    line5
}


#### Class Discussion
What _other_ letter do you think you could try other than `i`?

.
.
.
.
.
.
.
use `<C-d>` to go down...
.
.
.
.
da
// TODO: make a meme -- aliens..
Yes, `a` is the other.  I have never heard a great reason why, but just deal
with it.

so lets try again. try `da{`

if (true) {
    line1
    // Some distance
    line2
    line3

    line4
    line5
}

well shoot...

#### Class Discussion
Lets solve this together

if (true) {
    line1
    // Some distance
    line2
    line3

    line4
    line5
}

.
.
.
.

For those that couldn't wait or got the answer. `va{Vd`

#### Use YOUR SUPER POWERS
lets redo the previous exercise except copy from one if statement and override
lets redo the previous exercise except copy from one if statement and override
the next if statement.  How would we go about this?
the next if statement.  How would we go about this?

* DO

#### THIS is Really Cool!!!
yi{  yank between the {}
10j  jump down 10 lines
vi{ highlight everything between the {} in the next block of code
p    then paste the previous block of code over the one you are replacing


if (true) {
    line1
    // Some distance
    line2
    line3

    line4
    line5
}

if (true) {
    replace_me_1
    // Some distance
    replace_me_2
    replace_me_3

    replace_me_4
    replace_me_5
}



foo
bar
baz


foo
foo

baz


foo
bar
baz

replace_me_2
replace_me_3
replace_me_2

---------------------
# Summary of Super usefull Vertical Motions

#### Copy-pasting paragraphs & ContiguousCode

1. go into normal mode
2. put the cursor somewhere along the paragraph or codeblock
3. then hit leader y
this will prep the clipboard to copy text
4. then hit ap (this will select and copy the paragraph or codeblock
5. and paste it  below, or where ever you place the cursor.

            - AND -

#### Copy-pasting code blocks between {}

yi{  yank between the {}
10j  jump down 10 lines
vi{ highlight everything between the {} in the next block of code
p    then paste the previous block of code over the one you are replacing


if (true) {
    line1
    // Some distance
    line2
    line3

    line4
    line5
}

if (true) {
    replace_me_1
    // Some distance
    replace_me_2
    replace_me_3

    replace_me_4
    replace_me_5
}
