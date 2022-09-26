## Command Line Reference

`ls -lh` Outpost size in kB

`mkdir -p a/b/c` create parent directors as needed.

`mdir -pv a/b/c` verbose

## Wildcards in BASH

`*` anything

`?` one character

`ls foo.???` matches foo.txt and foo.jpg

`[]` specify characters

`ls foo[0-9].txt`  matches `foo0.txt` but not `foo01.txt`

`ls foo[^0-9].txt` matches `fooA.txt` not `foo0.txt`

`chmod +x dir` can cd into dir

`chmod +r dir` can read from dir

`chmod +w dir` can write in dir

`ls -ld` view ls for current directory

## vim

`ZZ` is the same as `:wq`

`5G` move to line f.

`1G` or `gg` move to the first line

`G` move to the last line

`:set nu` show line numbers
`:set number` show line numbers
`:set nonu` hide line numbers
`:set nonunmber` hide line numbers

`u` undo
`^r` redo
`U` undo current line only


# grep

`egrep -i 'sql|join' sqlnotes.txt` This finds sql or join in sqlnotes.txt (case insensitive)

`egrep '^SELECT'` sqlnotes.txt` This finds lines staring with SELECT


[reference](https://ryanstutorials.net/linuxtutorial)
