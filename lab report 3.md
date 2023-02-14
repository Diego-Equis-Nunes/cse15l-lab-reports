# Lab Report 3

# Researching Commands

The command `grep` is used to search for patterns within files using a string to print the specified result. This document will be exploring examples of different command line options for the `grep` command to achieve different results. The foled `written_2/` will be searched through using the various `grep` commands present. 

## grep -rl

The command `grep rl` is a quick way to recursively search files for a line. The `-r` aspect does the recursion, while the `-l` is responsible for listing file names. Running the command returns the file with the target word specified. The command is written as `grep -rl "<target_word>" <file_path>` and searches for the target word in the specified file path and returns all files with the word. To read directly about `grep -rl` you can read [this article](https://alvinalexander.com/linux-unix/recursive-grep-r-searching-egrep-find/#:~:text=grep%20%2Drl%20alvin%20.,i%20for%20case%2Dinsensitive%20searches) with all the details.

Running `grep -rl` in written_2/ using the command

`$ grep -rl "vistas" written 2_/`

Would return

`
written_2/travel_guides/berlitz1/IntroDublin.txt
written_2/travel_guides/berlitz1/IntroLakeDistrict.txt
written_2/travel_guides/berlitz1/IntroMadeira.txt
written_2/travel_guides/berlitz1/WhereToIbiza.txt
written_2/travel_guides/berlitz1/WhereToIsrael.txt
written_2/travel_guides/berlitz1/WhereToJerusalem.txt
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhereToMadeira.txt
written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
written_2/travel_guides/berlitz2/Costa-WhereToGo.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
`

describe, what its doing + why its useful

code block ex

describe, what its doing + why its useful

## grep -rc

The command `grep rc` recursively searches files for a pattern and returns the count of lines with that pattern. The `-r` aspect triggers the recursion, while the `-c` is responsible for listing the count. Running the command returns the count of lines with the target word specified. The command is written as `grep -rc "<target_word>" <file_path>`. To learn directly about `grep -rc` you can read [this source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) that I referenced.

code block ex

describe, what its doing + why its useful

code block ex

describe, what its doing + why its useful

## grep -rw

The command `grep rw` recursively searches for a targeted word and returns all lines with that entire word. The `-r` aspect triggers the recursion, while the `-w` functions to find the target word and the file and line it is in. Running the command returns the files with the word and the lines of text within the files that the word is in. The command is written as `grep -rw "<target_word>" <file_path>`. To learn directly about `grep -rw` you can read [this source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) which I referenced.

code block ex

describe, what its doing + why its useful

code block ex

describe, what its doing + why its useful

## grep -rn

The command `grep rn` recursively searches for a targeted word and returns a numbered list of all lines with that word. The `-r` is responsible for the recursion, while the `-n` functions to find the target word, its file and line. Running the command returns the lines of the files with the word in numbered order. The command is written as `grep -rn "<target_word>" <file_path>`. To learn about `grep -rn` you can read [this source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) that I used as a reference.

code block ex

describe, what its doing + why its useful

code block ex

describe, what its doing + why its useful

