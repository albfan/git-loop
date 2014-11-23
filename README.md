# git-status-interactive

A helping hand to deal with your messy repo

## Intro

**git-status-interactive** is a proof of concept for a desired expansion of *git status*

    $ git status --interactive

in the same way that *git add --interactive* helps with complex addings

## Features

- List files touched or new
- list files in new directories
- perform diff, add, rm, reset, checkout on selected files
- launch global commands (commit, pull, push) without exiting *git status-interactive* loop
- custom commands an action: Add your favourite commands and alias to loop

```
$ git config status-interactive.global-command <list of alias>
$ git config status-interactive.<key>-command <list of alias>
```

These are mine

```
[status-interactive]
   global-command = recommit rework
   diff-command = tdiff
```

See my [dotfiles](https://github.com/albfan/dotfiles/blob/master/gitconfig) for explanation of this alias

## Usage

Link script to your *PATH*:

    $ git clone <repo>
    $ cd <repo>
    $ ln -s git-interactive-status ~/bin/

Optional: create an easier alias
    
    $ cat <<EOF > ~/.gitconfig
    [alias]
        statusi = status-interactive
        si = status-interactive #short format
    EOF

Use it:

    $ git status-interactive #or git statusi

    1)  M file1
    2) ?? dir
    3) commit
    4) push
    5) pull
    6) quit

     file> 1

    1) diff
    2) add
    3) rm
    4) checkout
    5) reset
    6) quit

     action (file1)> 1
    ....
    + added this
    - deleted that
    ....

     action> 2

    1) M  file1
    2) ?? dir
    3) commit
    4) push
    5) pull
    6) quit

     file> 2

    listing files in (dir)

    1) file2
    2) file3
    3) quit

     dir> 1

    1) add
    2) less
    3) quit

     action> 2

    file2 contains this

     action> 1

    1) M  file1
    2) A  dir/file2
    3) ?? dir/file3
    4) commit
    5) push
    6) pull
    7) quit

     file> 7  #or type quit

    $

## Contribution

This snippet is focus on make your life easier, so any contribution is appreciated. It is evolving by rating "benefit/time" so if you have time, is pretty sure your PR will be accepted. Feel free to open issues or send PR.

By now, read the **TODOs** inside the script to find something useful to work on. Clearly a big step will be to recode script in perl

