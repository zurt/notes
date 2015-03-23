# Vim notes

## Current Configuration

### Plugins
-   Pathogen                [Link](https://github.com/tpope/vim-pathogen)
-   closetag.vim            [Link](http://www.vim.org/scripts/script.php?script_id=13)
-   ctrlp                   [Link](https://github.com/kien/ctrlp.vim)
-   dirdiff                 [Link](https://github.com/will133/vim-dirdiff)
-   html5.vim               [Link](https://github.com/othree/html5.vim)
-   matchit                 [Link](http://www.vim.org/scripts/script.php?script_id=39)
-   Syntastic               [Link](https://github.com/scrooloose/syntastic)
-   vim-airline             [Link](https://github.com/bling/vim-airline)
-   vim-fugitive            [Link](https://github.com/tpope/vim-fugitive)
-   vim-mustache-handlebars [Link](https://github.com/mustache/vim-mustache-handlebars)
-   vim-surround            [Link](https://github.com/tpope/vim-surround)

### Disabled
-   ternjs                  [Link](https://github.com/marijnh/tern)
-   ctags
-   NERDTree                [Link](https://github.com/scrooloose/nerdtree)

### Considering
-   Ag replacement for Ack  [Link](https://github.com/ggreer/the_silver_searcher)
-   JavaScript Indent       [Link](http://www.vim.org/scripts/script.php?script_id=3081)
-   JavaScript Libraries Syntax [Link](https://github.com/othree/javascript-libraries-syntax.vim)
-   neocomplcache           [Link](https://github.com/Shougo/neocomplcache.vim)
-   SuperTab                [Link](http://www.vim.org/scripts/script.php?script_id=1643)
-   tagbar                  [Link](https://github.com/majutsushi/tagbar)
-   vim-css-color           [Link](https://github.com/ap/vim-css-color)
-   vim-rails               [Link](https://github.com/tpope/vim-rails)
-   vim-bundler             [Link](https://github.com/tpope/vim-bundler)
-   YouCompleteMe           [Link](http://valloric.github.io/YouCompleteMe/)

### Color Schemes
-   wombat256mod
-   inkpot

## Learned through use

    $ \ls *.avi | vim -     Rename files in Vim
    :%s/.*/\='mv -iv '.submatch(0).' '.substitute(submatch(0),'\d\+-2015','2015','g')/g
    :'<,'>!bash
                            [Bulk rename files with Vim](http://vim.wikia.com/wiki/Bulk_rename_files_with_Vim)
                            [Using an expression in substitute command](http://vim.wikia.com/wiki/VimTip755)

    :%s#.*#                 For substitute when you need to match `/`. Delimiter can be any character.

    :n                      Next file
    :N                      Previous file

    $ vim -o a.txt b.txt    Open list of files into horizontal splits
    $ vim -O a.txt b.txt    Open list of files into vertical splits
    $ vim -p a.txt b.txt    Open list of files into tabs
    $ vim -p _*.scss        Open matching files into tabs

    :set ic?                Get value for `ignorecase` case sensitivity
    :set noic               Set `noignorecase`

    <C-a>                   Increment the number under the cursor

    Ctrl-G                  Show file status and location in file
    1 Ctrl-G                Show full file path

    :set spell              Turn on spellchecking
    :set nospell            Turn off spellchecking
    ]s                      Next mispelled word
    [s                      Previous misspelled word
    zg                      Add word to the dictionary
    zug                     Undo addition of a word to the dictionary
    z=                      Spelling suggestions

    :tabfir                 Short for :tabfirst
    :tablast                Jump to the last tab

    $ vim -R filename       Open file in read-only mode

    :g/^/m0                 Reverse lines

    :g!/pattern/d           Delete all lines that do not match pattern

    :g!/^\d\{3})/d          Delete all lines that do not start with three digits and close parathesis

    [Select all lines containing pattern and copy to a register](http://vim.wikia.com/wiki/Copy_search_matches)
    qaq                     Clear register `a`
    :g/pattern/y A          Append line matching pattern to register `a`

    :g/^$/d                 Delete all blank lines:

    ga                      Identify character under cursor in command mode
                            "Get Ascii": decimal, hex, and octal

    8232, Hex 2028, Octal 20050
                            [Line Separator U+2028](http://unicode-table.com/en/2028/)

    \r                      CR “carriage return”
    \n                      LF “line feed” or CRLF “newline”

    :%s/\%u2028/\r/gc       Replace line separator

    From ‘:help /\%x':

    \%d123                  Matches the character specified with a decimal number. Must be followed by a non-digit.
    \%o40                   Matches the character specified with an octal number up to 0377. Numbers below 040 must be followed by a non-octal digit or a non-digit.
    \%x2a                   Matches the character specified with up to two hexadecimal characters.
    \%u20AC                 Matches the character specified with up to four hexadecimal
    characters.
    \%U1234abcd             Matches the character specified with up to eight hexadecimal
    characters.

    :set list               Show invisibles
    :set nolist             Hide invisiibles
    :set list!              Toggle invisibles

    5. fo<C-v>5l3jrX						*v_b_r_example*

    abcdefghijklmnopqrstuvwxyz
    abc		defghijklmnopqrstuvwxyz
    abcdef  ghi		jklmnopqrstuvwxyz
    abcdefghijklmnopqrstuvwxyz

    abcdefghijklmnXXXXXXuvwxyz
    abc		defghijkXXXXXXrstuvwxyz
    abcdef  ghi		XXXXXXpqrstuvwxyz
    abcdefghijklmnXXXXXXuvwxyz

                            http://vim.wikia.com/wiki/Replace_a_word_with_yanked_text

    dw                      Cut word
    "_diwP                  Cut word into black hole and then paste from unnamed register.

    yiw                     yank word
    ciw<C-r>0               first paste (If at the start of the word then `cw<C-r>0` is sufficient.)
    .                       second paste and successive

    yiw                     yank word
    viwp                    first paste
    viw"0p                  second paste and successive

    yy                      yank line
    Vp                      first paste
    V"0p                    second paste and successive

    :%s/^\w\+\s\+//         Match one or more "word" characters starting at the beginning of the line
                            followed by at least one whitespace character, then remove them.

    :%s/^\s*\S\+\s*//       Match the first string of non-whitespace characters followed by a series
                            of whitespace characters, then remove them.

    gg qq dWj@qq @q         Macro to delete the first word of each line
                         gg Go to the first line
                         qq Record a macro into register `q`
                         dW Delete one word including the trailing space
                          j Go down one line
                         @q Run the macro in register `q`
                          q Stop recording the macro
                         @q Run the macro in register `q`

    :%norm dW               :normal replays the arguments as if typed in normal mode

    :set shellcmdflag=-ic   Bash doesn’t load your .bashrc unless it’s interactive.
                            Use to make Vim’s :! shell behave like your command prompt.

    gq                      Rewrap text to line length from :set textwidth=80.

    :let @" = expand('%:p') Copy full path and filename into the default (unnamed) register.

    :%!python -m json.tool  Pretty print json.

    `/s;\|s\ `              Search for multiple patterns at the same time!

    CTRL-Y                  While in completion mode, stop completetion and insert current selection.
    CTRL-E                  While in completion mode, stop completetion and insert nothing.

    :e                      Reload changes to the current file from disk. As simple as that.

    CTRL-K .3               Example of a digraph to create an ellipsis.
    CTRL-K "6               LEFT DOUBLE QUOTATION MARK
    CTRL-K "9               RIGHT DOUBLE QUOTATION MARK

    :Exp                    Shortcut for :Explore. Opens Netrw directory listing in current directory.
                            %   Create a new file in the current directory.
                            d   Create a new directory in the current directory.
                            TODO: Why do I get errors when creating a new directory?
                            Mac Terminal Vim 7.3.931

    :set filetype?          Display filetype setting for current split.
    :set syntax?            Display syntax settings for current split.

    :setlocal wrap          Set text to wrap in current buffer only. Useful for vimdiff.

    Quickly diff two buffers.
    :edit file1
    :diffthis
    :vnew                   Split the current view
    :edit file2
    :diffthis
    :diffoff                Turn diff mode off

    v_g_CTRL-G              Get more information about characters in selection (:help v_g_CTRL-G)

    :let @" = expand('%:t') Copy the name of the current file to the unnamed register

    <S-v>
    :norm yss<li>           Surround each of the selected lines with <li></li>

    :%s/>\s*</>\r</g        Break all tags to new lines

    :tabmove 0              Change the order of tabs. Indexed left to right starting at zero.

    :%norm! @q              Apply a macro to all lines.
    :5,10norm! @q           Apply a macro to lines 5 through 10.

    :r filename             Read a filename into the buffer. Short for :read filename

    :Errors                 Load Syntastic errors into location list.
    :lclose                 Close location list.

    Chrome vim plugin       http://vimium.github.io/

mksession seems to hold on to old .vimrc and pathogen settings. so I had to create a new one.
I should probably investigate further to figure out what's actually going on.

    :set filetype=mustache syntax=html
                            Set filetype and syntax for highlighting handlebars
    :set runtimepath?       Query current setting

    :help cmdline
    <S-Left>                Cursor one WORD right
    <S-Right>               Cursor one WORD left
    CTRL-B                  Beginning
    CTRL-E                  End

surround.vim
    ysiw<em>                Surround word under cursor with <em></em>
    cst<strong>             Change surrounding tag to <strong></strong>
    dst                     Delete surrounding tag
    S<p>                    In visual-line mode, surround line with <p></p>
    viws<a href="http://url.com">
                            Surround word under cursor with <a href="http://url.com">word</a>

    :b#                     Edit previous buffer

    g-                      Move backward in history
    g+                      Move forward in history

    :g/debugger/s//\/\/debugger/g
                            Replace debugger with //debugger throughout the whole file
    :g/\/\/debugger/s//debugger/g
                            Replace //debugger with debugger throughout the whole file

    U                       Uppercase selected text
    u                       Lowercase selected text
    ~                       Toggle case of character under cursor
    g~iw                    Toggle case on inner word

    ge                      Backwards word end (inclusive) word motion
    gE                      Backwards word end (inclusive) WORD motion

    :pwd                    Print current working directory
                            http://vim.wikia.com/wiki/Set_working_directory_to_the_current_file

    vim -p $(git diff --name-only HEAD~1 HEAD) -c "tabdo :Gdiff HEAD~1"
                            Diff each changed file between commits, loaded into tabs

    git difftool --tool=vimdiff --no-prompt HEAD~1 HEAD
                            Diff each changed file one-by-one

    :Gdiff                  Resolve merge conflicts using fugitive
                            http://vimcasts.org/episodes/fugitive-vim-resolving-merge-conflicts-with-vimdiff/
    //2  file  //3          3 splits are always: target branch | working copy | merge branch
    :diffget //2 | diffup   While in working copy, get change from target branch and update diff highlighting
    dp                      Short for `:diffput`
    ]c, [c                  Next, previous changeset
    :Gwrite                 Write working copy and close the other splits
    :Gwrite!                Write target or merge branch

    :only                   Close all other splits

    ctrlp.vim               Use <c-t> or <c-v>, <c-x> to open the selected entry in a new tab or in a new split.

    ?'/' + API + '/'        Search backwards for a string that normally needs escaping
                            http://stackoverflow.com/a/1550930

    Ctrl-e                  Moves screen up one line
    Ctrl-y                  Moves screen down one line

    :set so=999             Set `scrolloff` to a large value causes the cursor to stay in middle line
    :set so=0               Restores normal behavior

    :.,+5s/42/50/g          Search & replace from here (.) and the next 5 lines (+5)
    :.,$s/42/50/g           From here to the end of the file ($)
    :'<,'>s/foo/bar/g       Within visual selection

    shift_k                 Open a man page for the keyword under the cursor: more, ls, top

    :%s/\s\+$//             Trim trailing whitespace

    :SyntasticInfo          Show Syntastic settings for current file
    let g:syntastic_javascript_checkers = ['jshint']

    :g                      Operate on all lines matching pattern
    :g/^\s*$/d              Delete all empty lines
    :g!/pattern/d           Delete all lines that do NOT match pattern
    http://vim.wikia.com/wiki/Delete_all_lines_containing_a_pattern

    "_dd                    Use the black hole register to delete without storing in :reg

Rename a file
    :Explore                :e. is shorthand, but it may open NERDTree
    R                       Rename file
    <CR>                    Open the file for editing

Delete buffer
    :ls                     List open buffers
    :bdelete <buffer#>      Delete buffer number

Move backwards and forwards through cursor position history
    <C-o>                   Previous cursor position
    <C-i> or <Tab>          Next cursor position

Collapse line breaks
    J or <S-j>              Collapse current line with the next by removing <CR>

Case insensitive search
[Link](http://stackoverflow.com/questions/2287440/how-to-do-case-insensitive-search-in-vim)
    /\c{string}
    /{sting}\c
Also, review http://vim.wikia.com/wiki/Searching

Starting a session:
    vim -S secret.vim       Start the secret session
    :wall                   Write all modified files
    :mksession! secret.vim  Overwrite the secret session
    :source boring.vim      Load the boring session

Get the name of the current file:
[Link](http://vim.wikia.com/wiki/Get_the_name_of_the_current_file)
    <C-g>                   display the name of the file
    1<C-g>                  display the full path

    :echo @%                def/my.txt       directory/name of file
    :echo expand('%:t')     my.txt           name of file ('tail')
    :echo expand('%:p')     /abc/def/my.txt	 full path
    :echo expand('%:p:h')   /abc/def         directory containing file ('head')

Delete all lines of a file:
    gg                      Go to the beginning of the file
    dG                      Delete from here to the end of the file

This started working after installing vim through brew:
    "*yy                    Yank into the system clipboard
    "*dd                    Delete into the system clipboard
    "*p                     Paste from the system clipboard

Visual Line mode prepend to selected lines:
    :s/^/#                  Put '#' at the beginning of each line

Normal mode indentation:
    >>                      Indent right
    <<                      Indent left

[Link](http://www.vim.org/scripts/script.php?script_id=39)
    %                       matchit adds tag matching

    <C-w> <S-h,j,k,l>       push split to edge

[Link](http://vim.wikia.com/wiki/Format_a_code_block)
visual select
    =                       formats

[Link](http://stackoverflow.com/questions/2861627/vim-paste-in-insert-mode)
    <C-r> {register}        paste while in insert mode
    <C-r> *                 insert the contents of the clipboard
    <C-r> "                 insert the last delete or yank
    :h i_ctrl_r             help for this topic

[Link](http://vim.wikia.com/wiki/Highlight_current_line)
    :set cursorline         show cursorline in every window

only display the cursorline in the current window
    augroup CursorLine
    au!
    au VimEnter,WinEnter,BufWinEnter * setlocal cursorline
    au WinLeave * setlocal nocursorline
    augroup END

[Link](http://vimdoc.sourceforge.net/htmldoc/pattern.html#last-pattern)
    To clear the last used search pattern:
    :let @/ = ""

## Up and Running with vi with David D. Levine
[Link](http://www.lynda.com/vi-tutorials/brief-introduction-regular-expressions/170336/188825-4.html)

6.2 A brief introduction to regular expressions

* \(\) Repeats Multiple Items
    /\(ab\)*c matches "ababababababc"
* Greediness
  * `/<.*>` matches all of `<i>italic</i>`
  * `/<[^>]*>` matches only the opening tag of `<i>italic</i>`

6.4 Searching and replacing text

* & in the replacement text of a substitution will place the match:
  * `:%s/the[ym]/(&)/g`
    * "they or them" -> "(they) or (them)"
* Grouping
  * Switch "they them" to "them they": `:%s/\(they\) \(were\)/\2 \1/`

7.1 Indenting, auto-indent, and word wrap

* `i_CTRL-D` to delete one shiftwidth of indent at the start of the current line (while auto-indent is on).
* Auto-indent
  * `:set ai` enables auto-indent
  * `:set noai` disables auto-indent
* Wrap margin
  * `:set wm=8` enables wrap margin
  * `:set wm=0` disables wrap margin

## Your problem with Vim is that you don't grok vi
[Link](http://stackoverflow.com/questions/1218390/what-is-your-most-productive-shortcut-with-vim/1220118#1220118)

History of vi and other arcane knowledge. Probably more useful to read after a couple years of Vim use.

## A Vim Tutorial and Primer
[Link](http://www.danielmiessler.com/study/vim/)

- Contains a section on spelling and spellcheck.
- Contains a section on text objects. :help objects
- Contains a references section with links to useful resources.

    &                       Repeat last `ex` command.
    ~                       Change case.

    cc                      Delete line(s) into register and start insert linewise.
    c{motion}               Change from current position to {motion} and start insert.
    C                       Change the current line and start insert.
    s                       Substitute from current position and start insert.
    S                       Substitute the entire current line.

    <C-e>                   Scroll up one line.
    <C-y>                   Scroll down one line.

Modifiers
    i                       Inside
    cis                     Change Inside Sentence
    a                       Around
    gq{motion}              Format the lines that {motion} moves over.
    gqap                    Format Around Paragraph.

## Introduction to Vim Sessions
[Link](http://usevim.com/2013/07/05/sessions/)

    :mks {file}             Abbreviation for :mksession
    :so {file}              Source file to load it

## More Expressions
[Link](http://usevim.com/2013/06/28/expression-syntax/)

    i_CTRL-R =
    :echo $VIMRUNTIME
    :echo @a
    :echo 1 == 0 ? 'Yep' : 'Nope'
    :echo 'alex' =~ '^al'   Regular expressions
    :echo 'alex' ==? 'Alex' Case insensitive string comparisons

## Counting and Calculating with Vim
[Link](http://usevim.com/2013/06/14/counting-with-vim/)

    <C-a>                   Increment number under the cursor
    <C-x>                   Decrement number under the cursor
    <C-r>=                  Insert mode: Expression register for calculation

## Moving Windows
[Link](http://usevim.com/2013/06/07/moving-windows/)

    :help window-moving

    <C-w>T                  Move this window (split) to a new tab

## Terning Tricks
[Link](http://usevim.com/2013/05/24/tern/)

    let g:tern_map_keys=1   Enable keyboard shortcuts

    Shortcut          Command          Description
    <Leader>  td      :TernDoc         Documentation under cursor
    <Leader>  tb      :TernDocBrowse   Browse documentation
    <Leader>  tt      :TernType        Type hints
    <Leader>  td      :TernDef         Jump to definition (yes, 'td' is duplicated)
    <Leader>  tpd     :ternDefPreview  Jump to definition inside preview
    <Leader>  tsd     :ternDefSplit    Definition in new split
    <Leader>  ttd     :ternDefTab      Definition in new tab
    <Leader>  tr      :TernRefs        All references under cursor
    <Leader>  tR      :TernRename      Rename variable

    let g:tern_show_argument_hints='on_hold'  display argument type hints when cursor rests over func

## Spellchecker Wrangling
[Link](http://usevim.com/2013/05/10/synspell/)

Force spellchecking when editing XML (and HTML)
    :set spell
    :syntax spell toplevel
    <C-l>                   Force the screen to redraw

## Irregular expressions
[Link](http://usevim.com/2013/05/03/irregular-expressions/)

Vim regular expressions are not Perl-compatible!

Read more:
[Link](http://andrewradev.com/2011/05/08/vim-regexes/)
[Link](http://vimcasts.org/episodes/refining-search-patterns-with-the-command-line-window/)

## Practical: Joining and Splitting Text
[Link](http://usevim.com/2013/04/26/practical-registers/)

    J                       :help J

    <th>id</th>
    <th>Name</th><th>Age</th><th>Location</th>

    f/f>                    Move cursor to closing tag
    f/f>a<CR>               Same as above then insert line break
    qqf/f><CR><Esc>q        Record to q
    @q                      Run register q
    @@                      Repeat the previous register
    2@q                     Do it twice

## Practical: Registers
[Link](http://usevim.com/2013/04/19/practical-registers/)

    "acit
    "a                      Put the result in register a
    cit                     Change inner tag

## Decoding Tab Titles
[Link](http://usevim.com/2013/04/12/vim-101-decoding-tabs/)

:help 'tabline'
    +                       Unsaved file in this tab

## The Black Hole Register
[Link](http://usevim.com/2013/03/29/blackhole/)

    "_                      Disappear anything

    :let @a=@""             Copy the content of the unnamed register to a

## Pasting Into Command-line Mode
[Link](http://usevim.com/2013/03/15/vim-101-command-line/)

    CTRL-R                  Insert contents of a register in Insert or Replace mode

    "ayw                    Yank a word into register `a` in normal mode
    /                       Enter search
    CTRL-R + a              Put register `a`

    yw, /, CTRL-R + "       Shortcut using the default register

## Search as a Motion
[Link](http://usevim.com/2013/03/08/vim-101-motion-search/)

/ is a motion
    d/,<CR>                 Delete up to a comma

## Efficient HTML Editing with Text Objects
[Link](http://usevim.com/2013/03/01/vim-101-text-objects-for-html/)

at “a tag block”
it “innter tag block”

    <p><a href="http://example.com/1">This is a link</a> and <em>this is an emphasis</em>.
    <a href="http://example.com/2">This is another link</a>, which points to another page.</p>

    dat                     Remove text and tags surrounding cursor
    dit                     Remove text only within the tags surrounding
    cit                     Remove text only and enter insert mode

    a", a'                  Text object including quotes
    i", i'                  Text object inside quotes
    ci"                     Remove text inside quotes and enter insert mode

    ci>                     Change tag to another element


## Understanding 'listchars' (skipped)
[Link](http://usevim.com/2013/02/27/understanding-listchars/)

“The purpose of the 'list' (:help 'list') setting is to visualize tabs, spaces and line endings.”

## Object Motions
[Link](http://usevim.com/2013/02/22/vim-101-object-motions/)

    (, )                    Move by sentence (see :help sentence)
    {, }                    Move by paragraph (see :help paragraph)

## Vim After 11 Years by Ian Langworth
[Link](http://statico.github.io/vim.html)

    nmap <Leader>l :setlocal number!<CR>
    nmap <Leader>o :set paste!<CR>
    nmap <Leader>m :nohlsearch<CR>

    :b#                     Open the previously viewed buffer
    :e#                     Same as above

## The Jump and Change Lists
[Link](http://usevim.com/2013/02/15/vim-101-jumps/)

Jumps motions add jump list entries.

Examples of jumps are G, /, ?, n, N, L, M, H
-   Freely jumping around a file. Example: G
-   Jumping based on window size. Example: M
-   Text block jumps.             Example: (, ), {, }

    <C-i> and <C-o>         Forwards and backwards in the jump list
    :jumps or :ju           Display the jump list

    :changes                List of changes that can be undone
    g;                      Go to previous position in change list
    g,                      Go to next position in change list

## Practicing Marks
[Link](http://usevim.com/2013/02/08/easy-marks/)

    :marks                  List of all current marks
    ''                      Move to position before the last jump
    :jumps                  History of jumps

## Fancy Tags (skipped)
[Link](http://usevim.com/2013/02/01/vim-101-fancy-ctags/)

Sidebar tree visualization of tags.

## Preview Window
[Link](http://usevim.com/2013/01/25/preview-window/)

    :help preview-window    Only ever one preview window per tab
    :ptag tagname           Open tagname in preview window
    :ptag or :pta
    :ptnext / :ptprevious   or :ptn / :ptp
    :pclose or :pc          Close the preview window
    <C-w> }                 Open :ptag with the tag under the cursor
    <C-w> z                 Close the preview window

## The New Powerline
[Link](http://usevim.com/2013/01/23/vim-powerline/)

Some helpful tips on installation.

## Tags
[Link](http://usevim.com/2013/01/18/tags/)

Exuberant Ctags: http://ctags.sourceforge.net/ (Install via homebrew)

    $ brew install ctags
    $ cd src/
    $ ctags -R
    $ wc -l tags
    :set tags+=tags
    :tag text               Search for `text` in tags
    :tag /pattern           Search for `pattern` in tags
    <C-]>                   Jump to function definition
    <C-t>                   Go back

## The Core Skills
[Link](http://usevim.com/2013/01/11/vim101-core-skills/)

…

## Jumping Between Files
[Link](http://usevim.com/2013/01/04/vim101-jumping/)

    :help gf                Normal mode: type over text of file name and Vim will try to open it
    :help 'suffixesadd'     Help Vim figure out the file name
    :set suffixesadd+=.js   Vim will look for <filename>.js
    :set path?              View the current path
    :set path+=/new/path    Add a new path

    :help :find             Supports tab autocomplete
    :find filename          Type the name of a file to open it
    :tabfind filename       Open the file in a new tab

## runtimepath
[Link](http://usevim.com/2012/12/28/vim-101-runtimepath/)

    :set runtimepath?
    :help 'rtp'             List of every type of file that Vim searches for
    :runtime                Load files based on the 'runtimepath' (Pathogen modifies it to load plugins)
    $VIMRUNTIME             Locate documentation and plugins that ship with Vim

## Help Tags
[Link](http://usevim.com/2012/12/21/vim-101-help-tags/)

Must tell vim about new help files with :helptags
“Let's say you've installed rails.vim to ~/.vim/bundle/vim-rails because you use Pathogen, then to generate the help tags you'd have to type :helpt ~/.vim/bundle/vim-rails/doc.”

## Insert Mode Shortcuts
[Link](http://usevim.com/2012/12/14/vim-101-insert-mode-shortcuts/)

    :help ins-special-keys

Shortcuts for editing text while in insert mode:
    CTRL-w (:help i_CTRL-w) Delete the word before the cursor
    CTRL-u                  Delete the current line
    CTRL-[                  Quit insert mode and go back to Normal mode
    CTRL-r {0-9a-z"%#*+:.-=}
    CTRL-n (CTRL-p)         Invoke auto completion

Recover from accidental CTRL-u
    :reg .
[Link](http://vim.wikia.com/wiki/Recover_from_accidental_Ctrl-U)

Add to .vimrc (cannot put comments after inoremap!)
    inoremap <C-u> <C-g>u<C-u>
    inoremap <C-w> <C-g>u<C-w>
Now Ctrl-u and Ctrl-w will work as before, but they first use Ctrl-g u to start a new change, as far as undo is concerned
    :help i_CTRL-g_u        Starts a new change in insert mode

## The Vim Distribution

    $VIMRUNTIME/color       All of the available color schemes
    $VIMRUNTIME/syntax      All of the syntax files
    $VIMRUNTIME/macros      Home of matchit.vim (Run :help matchit-install)

## Operator-Pending Mode
[Link](http://usevim.com/2012/12/05/omap/)

Time between operator command and motion. A variant on normal mode.

    yw                      Yank the word under the cursor
The operator is said to be pending in the type between typing the operator
command and the motion. Addressable by mappings:
    :omap t it
Now typing dt will delete the text between an opening and closing tag.

## Let
[Link](http://usevim.com/2012/11/30/vim101-let/)

Additional variable outside of built-in settings.
Add g: to a variable name to refer to the global value.

    :let g:loaded_nerd_tree
    :let                    Show a list of all the variables
    :let b:current_syntax   Useful to check the current syntax filetype

## Auto Settings (skipped)
[Link](http://usevim.com/2012/11/23/vim-101-auto-setting/)

## Local Options
[Link](http://usevim.com/2012/11/16/vim-101-local-options/)

Options applied to the current window or buffer.
    :setlocal
    :setl                   Show all local options that differ from default
    :setl all               Show all local options
    :setl {option}<         Copy the global value to local
Useful if editing files of different types. Switch tab indentation for example.

## Options
[Link](http://usevim.com/2012/11/09/vim-101-options/)

:set
    :se                     Show all options that differ from default
    :set all                Show all options
    :se {option}?           Query a specific value
    :se {option}={value}    Set option to value
    :se number              Toggle line numbers on
    :se nonumber            Turn line numbers off (Prefixing boolean options with no turns them off)

## Repeatability
[Link](http://usevim.com/2012/11/07/repeatability/)

    .                       Repeat the last change
    @:                      Repeat the last command-line
    ;                       Repeat the last f and t command
    &                       Repeat the last :s substitution

## Set Hidden
[Link](http://usevim.com/2012/10/19/vim101-set-hidden/)

    :set hidden             Opening a new file when current buffer has unsaved changes causes files to be hidden instead of closed
    :ls                     Show buffers
    :b3                     Go to buffer 3

## ed and ex (skimmed)
[Link](http://usevim.com/2012/09/28/vim101-history/)

## Virtual Editing (skipped)
[Link](http://usevim.com/2012/09/21/vim101-virtualedit/)

    virtualedit             Allows block selections to operate across empty lines

## Working with Brackets (skipped)
[Link](http://usevim.com/2012/09/14/vim101-brackets/)


## External Help
[Link](http://usevim.com/2012/09/07/vim101-keywordprg/)

    K                       Run a program to lookup the keyword under the cursor
    setlocal keywordprg     Specify the name of the program to run (default "man")
    :help find-manpage
    :runtime ftplugin/man.vim

## Folding
[Link](http://usevim.com/2012/08/31/vim101-folding/)

    zf{motion}              Create a fold based on `motion`
    <visual>zf              Make a selection, then type `zf`
    zo                      Open a fold
    zc                      Close a fold
    zd                      Delete the fold under the cursor
    zE                      Eliminate all folds in the current window

## QuickFix and Grep (skipped)
[Link](http://usevim.com/2012/08/24/vim101-quickfix/)

## Windows
[Link](http://usevim.com/2012/08/17/vim101-windows/)

Windows are a viewport on a buffer. (It appears that these are splits)
    <C-w> q                 Close a window
    <C-w> -/+               Vertical window resizing
    <C-w> </>               Horizontal window resizing
    <C-w> <S-t>             Open the current window in a new tab

## Macros
[Link](http://usevim.com/2012/08/10/macros/)

    :help recording         About Macros
    qq                      Start recording and save the macro to register q
    <Enter some commands>
    q                       Stop recording
    :req q                  Show the macro exactly as it was typed
    @q                      Execute the contents of the q register
    3@q                     Execute q 3 times
    @@                      Repeat the last @

## Indentation
[Link](http://usevim.com/2012/08/03/vim101-indentation/)

    expandtab               Insert spaces
    softtabstop             Number of spaces to insert
    shiftwidth              Controls the number of spaces used with autoindent
    autoindent
    smartindent

## Undo
[Link](http://usevim.com/2012/07/27/vim101-undo/)

    :undol                  List undo branches
    :earlier 15m            Return buffer state to 15 minutes ago

    :help undo-branches
    :help undo-persistence

## What Is The Leader Key?
[Link](http://usevim.com/2012/07/20/vim101-leader/)

“The beauty of the <Leader> key is it effectively gives us a namespace for customized keyboard shortcuts.”

    <Leader>                leader key is \ by default
    let mapleader=","       add to .vimrc to set leader to ,
    :set timeoutlen         Set the timeout for next key in sequence after leader. (Vim waits 1000 milliseconds by default)

## Getting Help
[Link](http://usevim.com/2012/07/13/vim-help/)

Help is contextual
    :help subject           Search for help on subject
    v_                      Prepend for visual mode commands
    i_                      Prepend for insert mode commands
    :help i_CTRL-P          Display the help for completion
    :help 'write'           Use single quotes to find :set options

    set wildmenu            Tab completion

Navigation
    <C-]>                   Press over a term will attempt to jump to matching help subject
    <C-T>                   Jump back to the previous location

    :helpgrep or :helpg     Search. Accepts regular expressions. Use :helpg term\c to ignore case.
    :h                      Alias for :help
    :viu                    Shortcut for help on Normal mode. There are shortcuts to certain sections.


## *21.4* Sessions
[Link](http://vimdoc.sourceforge.net/htmldoc/usr_21.html#21.4)

    :mksession vimbook.vim  Create a session file
    :source vimbook.vim     Restore this session
    vim -S vimbook.vim      Start vim and restore this session

## Reload VIMRC
[Link](http://dailyvim.blogspot.com/2008/11/reload-vimrc.html)

If editing it currently, then
    :so %

    :source $MYVIMRC
    :so $MYVIMRC

    :echo $MYVIMRC

## Combining Operators and Motions
[Link](http://usevim.com/2012/06/22/vim101-selecting-motions/)

    y2as    yank two sentences into a register
        y   yank
        2   count argument for the following motion
        as  sentence

    yw      yank the current word under the cursor
    y5l     yank five characters to the right of the cursor

    >5$     indent the next five lines
        >   indent
        5   count argument for the following motion
        $   to the end of the line

## Tabs (Fuck yeah tabs! (Don't know why I'm so excited about this…))
[Link](http://usevim.com/2012/06/08/js101-tabs/)

    :help tabpage        Tabs can hold multiple split windows!
    vim -p file1 file2   Open several files into tabs.

    :tabnew or :tabe     New tab (tabe is short for “tabedit”)
    :tabc                “tabclose”
    :tabc!               Close even if the buffer has changes
    :tabc 3              Close the third tab

    :tabn / :tabp        “tab next” / “tab previous”
    gt / gT              same as above but way betterer

    :tabs                shows a list of tabs
    :tabdo {cmd}         execute {cmd} in each tab page ( or :tabd )
           :tabd %s/Rake/Make/ec   (e for ignore errors like “pattern not found”)

## FileType-Specific Commands (skipped)
[Link](http://usevim.com/2012/06/06/filetype/)

    :help autocommand
    :help :au
    :help :set
    :help autocmd-events-abc

## Repeating commands
[Link](http://usevim.com/2012/06/01/vim101-repeating-commands/)

    n/N   next and previous for text search /, ?
    &     repeat the :s (substitute) command
    	but it's probably more efficient to use the c flag with global substitution:
    	:%s/example/Example/gc
    .     repeat the last *text changing* command
            one example is to type .html_safe <Esc> then move cursor and hit .
    ;/,    forward and back while using f/F and t/T to search a line

## Text Object Editing Tricks
[Link](http://usevim.com/2012/05/25/vim101-text-objects/)

while cursor is on the first of a pair
    ci<   replace everything inside the <>
    ci"   replace everything inside the ""
          c{motion}
    	c  change
    	i" select text from the previous quote to the next quote (actually an argument to the change command)
    yi"   yank everything inside

    <html>
      <head>
        <title></title>
      <body>
        <h3>Big time "player"</h3>
      </body>
    </html>

## Blockwise Visual Mode
[Link](http://usevim.com/2012/05/18/vim101-visual-mode-2/)

    <C-v>   enter visual block mode
    I       "block insert"

## Using a Mouse with Vim (skipped)
[Link](http://usevim.com/2012/05/16/mouse/)

## Visual Mode
[Link](http://usevim.com/2012/05/11/visual/)

from normal mode
    v     switch to visual mode
    gv    switch into visual mode with the last selection
    #v    reselect the last selection, multiplied by the number (broken)

from visual mode
    o     go to the other end of the selection
    <     shift left
    >     shift right
    ~     switch the selection's case
    !     filter the selection through an external command
    :     to enter Ex commands (make a selection, then press :, then enter a regular expression)

## Marks (skipped)
[Link](http://usevim.com/2012/05/04/marks/)

## Vim Splits - Move Faster and More Naturally
[Link](http://robots.thoughtbot.com/post/48275867281/vim-splits-move-faster-and-more-naturally)

    :sp   horizontal split
    :vsp  vertical split
    :10sp specify height with number prefix

Easier Split Navigations
    nnoremap <C-J> <C-W><C-J>
    nnoremap <C-K> <C-W><C-K>
    nnoremap <C-L> <C-W><C-L>
    nnoremap <C-H> <C-W><C-H>

More Natural Split Opening
    set splitbelow
    set splitright

Resizing Splits
    <C-w> _  Max out the height of the current split
    <C-w> |  Max out the width of the current split
    <C-w> =  Normalize all split sizes

More Split Manipulation
    <C-w> r  Swap top/bottom or left/right split
    <C-w> T  Break out of current window into a new tabview
    <C-w> T  Close every window in the current tabview but the current one

## learn vim progressively
[Link](http://yannesposito.com/scratch/en/blog/learn-vim-progressively/)

superpowers
move on current line:
    0 ^ $ g_ f F t T , ;
    dt"  remove everything until the "

visual mode zone selection
    a for "all" and i for "inside"
    <action>a<object>
    <action>i<object>
    action could be: d (delete), y (yank), v (select in visual mode)
    object can be: w (word), W (extended WORD), s (sentence), p (paragraph) or natural such as ",',),},]
    (map (+) ("foo"))

select rectangular blocks
    <C-v> Start block selection
move
    I-- [Esc] write "-- " to comment each line

completion
    start typing in insert mode, then hit <C-n> or <C-p> for next and previous completion match
    <C-n>
    <C-p>

macros
    1
    put the cursor on a line with only "1" qaYp<C-a>q
    qa   start recording
    Yp   duplicate this line
    <C-a> increment the number
    q stop recording
    @a   do the action in a
    @@   do the last action
    100@@ do the last action 100 times

Visual Selection: v, V, <C-v>
Once the selection has been made:
    J    join all the lines together
    < or >  indent to the left or right
    =    auto indent
Example of auto indent a function:
    // S-V => Visual line select
    // $   => Go to the end of the line such that cursor is on the {
    // %   => Go to the matching }
    // =   => Auto indent
Example of adding something at the end of all visually selected lines:
    <C-v>
    go to the desired line (jjj or <C-d> or /pattern or % etc...)
    $ go to the end of the line
    A, write text, [ESC]

Splits: :split and vsplit
    :split  create a split (:vsplit create a vertical split)
    <C-w><direction>  to switch between splits, where dir is any of hjkl
    <C-w>_ (or <C-w>|)  to maximize the size of the split (or vertical split)
    <C-w>+ (or <C-w>-)  to grow split (or shrink split)
    :q   to close a split

Movement
    %    go to the corresponding (, {, [, ], }, )
    *    go to next occurence of the word under the cursor
    #    GO TO PREVIOUS OCCURENCE OF THE WORD UNDER THE CURSOR

    w    go to the start of the following word
    e    go to the end of this word
    W    go to the start of the following group of characters separated by blank
    E    go to the end of the following group of characters separated by blank

    .    repeat the last command
    #.   repeat the last command # of times

Saving
    :e <path/to/file> → open
    :saveas <path/to/file> → save to <path/to/file>
    :x, ZZ or :wq → save and quit (:x only save if necessary)
    :qa   close all tabs and splits and quit vim
    :q! → quit without saving, also: :qa! to quit even if there are modified hidden buffers.
    :bn (resp. :bp) → show next (resp. previous) file (buffer)

Basics
    cw    replace from the cursor to the end of the word
    ^     go to the first non-blank character of the line
    g_    go to the last non-blank character of the line

## Walking without crutches
[Link](http://walking-without-crutches.heroku.com/)

    f/F    land on the match
    t/T    stop one short of the match
    f{char};;;
    ;      repeat
    ,      reverse
    d{motion}
    c{motion}

Return to slide 124/136 to review Text Objects
    ""
    a" - a quoted string
    i" - inner quoted string
    ()
    ab - a block
    ib - inner block
    {}
    aB - a Block
    iB - inner Block
    <a>tag</a>
    at - a tag block
    it - inner tag block

## Grok
[Link](http://stackoverflow.com/questions/1218390/what-is-your-most-productive-shortcut-with-vim/1220118#1220118)

    J      join lines
    :.,+3j from current line to 3 lines down
    :.,$j  from current line to last line
    :%     is synonymous with :1,$ (all the lines)

    v      v is for converse
    :%v/.../d

## :help

    :set mouse=a enable mouse in xterm
    Ctrl-] cursor on tag, jump
    Ctrl-T, Ctrl-O to go back

    :help word Ctrl-D  see matching entries for 'word'
    :helpgrep


## vimtutor

    r      replace operator
    rx     replace the character at the cursor with x
    c      change operator
    ce     delete from cursor until the end of the word, go to insert mode

    Ctrl-G show file status and location in file

    G      go to last line
    gg     go to first line
    #G     go to line number #

    /test  search forward for text
    ?text  search backward for text
    n      next occurence
    N      previous occurence
    Ctrl-O go back to previous cursor position
    Ctrl-I go forward to next cursor position

    %      go to matching (,[,{,},],)

    :!     run external command

    v      visual mode
    :      operate on selection
    :w FN  write to new file FN

    :r FN  read file (normal mode)
    :r !ls read output of the ls command

    R      replace mode writes over

    :set ic  ignorecase for search (:set noic)
    :set hls highlight search (:set nohlsearch)
    :set is  show partial matches for a search phrase
    /text\c  ignore case for just one search

    :h     help
Ctrl-W Ctrl-W to jump between windows

    :e ~/.vimrc
    :r $VIMRUNTIME/vimrc_example.vim
    :h vimrc-intro

    :set nocp  vim is not in compatible mode
    :e Ctrl-D shows list of commands starting with "e"
    <TAB> complete

## Everyone Who Tried to Convince Me to Use Vim Was Wrong
[Link](http://yehudakatz.com/2010/07/29/everyone-who-tried-to-convince-me-to-use-vim-was-wrong/)

    ci     start with cursor on the character to change
    ci "   replace what's inside of the next set of " and go to insert mode
    ci (   replace what's inside of the next set of ( and go to insert mode

## Vim From Essentials to Mastery
[Link](http://www.infoq.com/presentations/Vim-From-Essentials-to-Mastery)

Bill Odom from vimgeeks.org

Insert mode:
    i a c o r s
    I A C O R S
    Ctrl-o temporarily exit insert mode
    gj move screen line rather than physical line
    gk
    zz, zb, zt position scroll without moving cursor
    * start searching for word under cursor forward
    # start searching for word under cursor backward
    Ctrl-N completion
    Ctrl-P
    Ctrl-X+Ctrl-?
    . redo the last thing you did
    . redo the last thing you did
    . redo the last thing you did

:reg
    26 name registers from "a to "z
    Uppercase the name to append to register
    "1 through "0 tracks recent deletes
    "- last "small" delete

    "_ black hole forgets everything put in it
    "/ last search

    ". last inserted text
    ": last Ex command
    "% current filename
    "# alternate filename

    "* system clipboard (OS X)
    "*yy yank the current line into the OS X clipboard
    "*p paste from the OS clipboard
    "+ system selection (X11)

    "<register><operator>
    :set clipboard=unnamed (link unnamed register and OS clipboard)

    "gdd delete line into g register
    "gp put line from g register
    <Ctrl-R><register> while in insert mode, put register

## Movement in Command-line Mode
[Link](http://usevim.com/2012/04/27/command-line-mode/)

:
    Ctrl-B              (beginning of line)
    Ctrl-E              (end of line)
    Ctrl-R              (insert value of register)

## CTRL-R
[Link](http://usevim.com/2012/04/20/c-r/)

While in insert mode...
    Ctrl-R a            (paste a register at location w/o leaving insert)
    Ctrl-R =60*60*24    (expression register)

## Registers
[Link](http://usevim.com/2012/04/13/registers/)

    :reg                (see all current registers)
    dd                  (delete a line)
    yy                  (yank a line)
    unnamed             ("" register holds deleted or yanked)
    "0p                 (the 0 register always holds the last yank)
    "ayy                (yank the current line into register a)
    "ap                 (put register a)


## Search and Replace on Multiple Files
[Link](http://usevim.com/2012/04/06/search-and-replace-files/)

    vim *.js                (open all the .js files into buffers)
    :arg                    (display the argument list)
    :arg *.rb               (replace old argument list with all matching files)
    :argadd
    :argdel
    :argdo                  (execute commands for all files in arg list)
    :argdo %s/cmd/command/ge (e flag to ignore errors for files with no match)
    :argdo %s/cmd/command/ge | update (update to write the files)
    :update                 (write the files)
    :bufdo                  (update all buffers)
    :windo                  (update all windows)

## Cut, Copy and Paste Using Visual Selection
[Link](http://vim.wikia.com/wiki/Cut/copy_and_paste_using_visual_selection)

    u                   (undo)
    U                   (return a line to its previous state, keeps history!)
    Ctrl-R              (redo)
    v visual selection
    d "delete" to cut
    y "yank" to copy
    c delete selection and enter insert mode in place
    p paste after cursor
    P paster before cursor

## Search and Replace
[Link](http://usevim.com/2012/03/30/find-and-replace/)

    :substitute
    :s
    :s/search/replace   (operates on the first match on the current line)
    :s/search/replace/g (all matches on current line)

    :global
    :g                        (global)
    :g/Empire/s//Wookies/g    (match globally and then apply command)
    :%s/Empire/Wookies/g      (range all lines in file)
    :1,10s/Ewoks/Care Bears/g (range lines 1 through 10)
    :1,10s/Ewoks/Care Bears/i (case-insensitive match)
    :%s/star/blackhole/gi     (match all lines, all occurences and case-insensitive)
    :%s/star/blackhole/gic    (confirm each substitution)

## Buffers
[Link](http://usevim.com/2012/03/23/buffers/)
[Link](http://vim.wikia.com/wiki/Vim_buffer_FAQ)

    :ls       (list buffers)
    :buffers  (same as :ls)
    :buffer # (make # buffer active)
    :ball     (open all buffers in windows)
    :vertical ball (vertical windows)
    :sbuffer #(open a specific buffer in a new window)
    :bdelete #(delete buffer)
    :bn       (next buffer (or :bnext))
    :bp       (previous buffer (or :bprevious))

## Editing Remote files
[Link](http://usevim.com/2012/03/16/editing-remote-files/)

    vim scp://server/file
    vim scp://kurt@shortname.example.com/.vimrc

    ~/.ssh/config
    host shortname
      User kurt
      Hostname shortname.example.com
      Port 9372

## Quick Movement
[Link](http://usevim.com/2012/03/09/quick-movement/)

Half screen movement
    ctrl u  (up)
    ctrl d  (down)

Full screen movement
    ctrl f  (forward)
    ctrl b  (back)

Line alignment of current line
    z enter (top)
    z .     (middle)
    z -     (bottom)

With screen movement
    H       (home)
    M       (middle)
    L       (last)

Word movement
    w       (start of word)
    e       (end of word)
    b       (beginning of previous word)

    W,E,B   (don't count symbols or punctuation as separate words)

Text Block Movement
    (       (previous sentence)
    )       (next sentence)
    {       (previous paragraph)
    }       (next paragraph)

Related item
    %       (next or previous: brackets, comments, preprocessor)

Line Movement
    #G      (go to line number, just G -> last line)
    gg      (first line)
    ``      (back to the last position)

Character Movement
    f{char} (next occurence on line)
    F{char} (previous occurence on line)
    #f      (#th occurence)
    t/T     (move before matching character)
    ; to repeat

## Install the latest version of vim with Homebrew
-   Install homebrew: $ ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
-   If brew is already installed (perhaps it comes with Xcode?), then: $ brew update
-   Install Xcode Command Line Tools
-   $ brew install mercurial (required for vim)
-   $ brew install vim
-   $ sudo vim /etc/paths (Move /usr/local/bin in front of /usr/bin)
-   $ which vim

## Seven habits of effective text editing
[Link](http://www.moolenaar.net/habits.html)
