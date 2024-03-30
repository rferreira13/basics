Using [git config](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

Flags to git config:

- git config --system
    - Uses [path]/etc/gitconfig file
    - Contains values applied to every user on the system and all their repositories
    - Need administrative or superuser privilege to make changes to it

- git config --global
    - Uses ~/.gitconfig or ~/.config/git/config file
    - Values specific personally to the user

- git config --local
    - Uses file in the Git directory (that is, .git/config)
    - Need to be located somewhere in a Git repository for this option to work properly

View all settings

> git config --list --show-origin

Identity

> git config --global user.name "John Doe"

> git config --global user.email johndoe@example.com

[Editor](https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Setup-and-Config#ch_core_editor)

> git config --global core.editor code

Default branch name

> git config --global init.defaultBranch main

Check settings

> git config --list

> cat ~/.gitconfig

---

[Initializing git](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)

> cd /home/user/my_project

> git init

---

Using .gitignore

- ignore all .a files
> *.a

- but do track lib.a, even though you're ignoring .a files above
> !lib.a

- only ignore the TODO file in the current directory, not subdir/TODO
> /TODO

- ignore all files in any directory named build
> build/

- ignore doc/notes.txt, but not doc/server/arch.txt
> doc/*.txt

- ignore all .pdf files in the doc/ directory and any of its subdirectories
> doc/**/*.pdf



