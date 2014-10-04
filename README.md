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

## Usage

Link script to your *PATH*:

    $ git clone <repo>
    $ cd <repo>
    $ ln -s git-interactive-status ~/bin/

Optional: create an easier alias
    
    $ cat <<EOF > ~/.gitconfig
    [alias]
        statusi = status-interactive
    EOF

Use it:

    $ git status-interactive #or git statusi
    1) file1
    2) dir
    3) quit
     file>1
       actions for (file1)
    1)diff
    2)add
    3)rm
    4)checkout
    5)reset
    6) quit
     action>1
    ....
    + add this
    - delete that
    ....
     action>2
     action>6
    $

## Contribution

This snippet is focus on make your life easier, so any contribution is appreciated. It is evolving by rating "benefit/time" so if you have time, is pretty sure your PR will be accepted. Feel free to open issues or send PR.

By now, read the **TODOs** inside the script to find something useful to work on. Clearly a big step will be to recode script in perl

