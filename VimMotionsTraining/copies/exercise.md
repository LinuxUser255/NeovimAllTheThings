# Advanced Vim/Neovim Motions


## Practice advanced motions on this document. Just follow instructions
### How to use this md file:
**!! _Copy the raw markdown version of this doc, opent it in Vim, and use it for practice_ !!**



### Change
you delete the line, and go into insert mode
so, to delete a line you do: dd
but to do the same except land in insert mode you do: cc
it's just like d, but lands you in insert mode.
`c` is a powerful motion.  You use it just like `d` but at the end of the
motion you are ejected from `NORMAL` and into `INSERT`.

So if you wished to delete a word and then type in a new word, `c` is a great
habit to form.

Lets see the difference

// dd this line
// cc this line

### Horizontal Movement
Lets learn about!: `_`, `0`, `$`, `D`, `C`, `S`, `f`, `,`, `;`, `t`, `F`, and `T`

- `_`, Under Score: go to begining of the line:
and goes to first non-whitespace char
lands you in normal mode
- `0` Zero goes all the way to beginning of the line:
-`^` Carret does this too
-`$`, Dollar jumps to EOL:
-`D`, deletes everything past the cursor to the left. like using backspace in insert mode
also, if you had something like: foobar fooBar fooBar, by placing the cursor
at on the first letter of the second word, then you delete every proceeding character after

`foobar foobar fooBar fooBar fooBar fooBar`

`C`, deletes one past the cursor to the left. but lands in insert mode

`foobar foobar fooBar fooBar fooBar fooBar`


`S`, deletes the whole line, respects indenting, and go into insert mode.

`s`, deletes single char, then goes into insert mode

`f`, jumps to first occurance of specified letter
example:
Jump to the capital B in fooBar. the 2nd word below, in the middle, the middle second one
in norm: fB, this jumps to the first occurance of capital B on that line
    foobar foobar foobar
And, using semicolin `;`, will jump to the next capital T

`,`, comma to jump backwards

`;`, will jump to the next capital T

`t`, jumps to the char, but not on or past

`F`, does wat lower t does but moves in in revese
    foobar foobar foobar

`T` so placing the cursou on the b in the last occurance of fooBar,
them type FB, will jump to the immediate previous occourance of capital B
so, that's the cap B in the second word, then, ; and , does the same jump between, but in reverse

!!!!! ---- Super cool & useful ------ !!!!!
To delete the foobar of an if statement,one way you can do is just dt)
close. jumped up until the closing parentheses and closed everything
// place cursor on t , then press dt shift 9
// also can do the same but use ct, lands you in insert mode
if (true, true) {
    foobar fooBar fooBar
}

// can be used on multiple params&args and commas
// delete the middle occourance of true: df space
if (true, true, true) {
    foobar fooBar fooBar
}


// can be used on multiple params&args and commas
// delete the middle occourance of true: df space
if (true, true, true) {
    foobar fooBar fooBar
}


// How would we move around on the line with "foobar"
if (true) {
    foobar foobar foobar
}



### Vertical Movement
#### Core movement
Rely on relative jumps.  Get good at them.

If you get NeoVim, try VimBeGood

#### { and }
We know about search.  That is a vertical movement, but its really specific.

First lets talk `{` and `}`
 `{` and `}` used to jump to from top and bottom of blocks of code

Place { on the first line, and press closing curlly brace, and now your at the end of the code block

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
.

.

.

.

.

.

.

.

.

.

.

.

.

.

.

.

.

.

.

.

.

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
when cursor is on a { by pressing % you jump to the next squirlly brace

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

delete that block by doing that by doing a shift v jumping to the end,jump to
the matching, delete those lines, It just feels super cool
- select a whole block & delete it:
- on first line
- do: Shift v + f{%d
- can also copy it with y instead of d

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

- try again, but yank, instead of delete
- on first line, if,
- do: Shift v + f{%y


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
foobar of the if statement?

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
place the cursor in the code block, and do `di}`
that deletes everyting inside the matching {}
also works with `ci}`


if (true) {
    line1
    // Some distance
    line2
    line3

    line4
    line5
}

can also yank the contents: `yi}`


First, place your cursor _in_ the if statement.  Where ever you want.  Type `di{`

i = inside


#### Class Discussion
What _other_ letter do you think you could try other than `i`?
a
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
.
.
.
.
.
.
.
.
.
.
.
.
.

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
.
.
.

For those that couldn't wait or got the answer. `va{Vd`

#### Use YOUR SUPER POWERS
lets redo the previous exercise except copy from one if statement and override
the next if statement.  How would we go about this?

So I want to take what's inside this squirrely bait or this if statement andput
it into the other if statement.
place cursor in the first block, and

`yi}`

`10j` jump down by 10

`vi}` highligts everything inside, then

`p` paste in the contents


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



#### Use YOUR SUPER POWERS do it again
lets redo the previous exercise except copy from one if statement and override
the next if statement.  How would we go about this?

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

#### deleting part of a line, usefull in C++
Highlight from within the word
place cursor in/on middle of word, and do diw, viw, ciw, etc.
viW: highlights everything including non contiguous white space
makes editing strings and text faster
```c++

int main()
{
    std::cout << "Play a game? (y/n): ";
    char response = std::tolower(std::getchar());
    std::cout << "you entered: " << response << '\n';
    if (response == 'y')
    {
        std::cout << "OK, let's play..\n";
        std::cout << "Choose difficulty level? hard medium easy: ";
        std::string difficulty;
        std::cin >> difficulty;

        if (difficulty == "easy" || difficulty == "medium" || difficulty == "hard")
        {
 ......
    system("pause");
    return 0;
}
```


```c++

int main()
{
    std::cout << "Play a game? (y/n): ";
    char response = std::tolower(std::getchar());
    std::cout << "you entered: " << response << '\n';
    if (response == 'y')
    {
        std::cout << "OK, let's play..\n";
        std::cout << "Choose difficulty level? (easy/medium/hard): ";
        std::string difficulty;
        std::cin >> difficulty;

       //std::cin >> difficulty;
       //std::cin >> difficulty;

        if (difficulty == "easy" || difficulty == "medium" || difficulty == "hard")
        {
 ......
    system("pause");
    return 0;
}

```

### copy pasting over text/lines
```lua
-- Pasting highlighted text over a pre-selected highligted text
-- Deletes highlighted word into the 'void' register and then paste it over.
vim.keymap.set("x", "<leader>p", [["_dP]])
```
using this remap ^^^^

Goal:
copy foo, and paste it over bar
Ctrl + v + y.  or just yy to yank it
then, highlight bar, and do <leader>p

foo
bar
baz

and `{dap` deletes a paragraph, deletes outsides of the paragraph


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
