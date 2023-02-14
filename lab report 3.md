# Lab Report 3

# Researching Commands

The command `grep` is used to search for patterns within files using a string to print the specified result. This document will be exploring examples of different command line options for the `grep` command to achieve different results. The foled `written_2/` will be searched through using the various `grep` commands present. 

## grep -rl

The command `grep rl` is a quick way to recursively search files for a line. The `-r` aspect does the recursion, while the `-l` is responsible for listing file names. Running the command returns the file with the target word specified. The command is written as `grep -rl "<target_word>" <file_path>` and searches for the target word in the specified file path and returns all files with the word. To read directly about `grep -rl` you can read [this article](https://alvinalexander.com/linux-unix/recursive-grep-r-searching-egrep-find/#:~:text=grep%20%2Drl%20alvin%20.,i%20for%20case%2Dinsensitive%20searches) with all the details.

Running `grep -rl` in `written_2/` using the command

`$ grep -rl "vistas" written 2_/`

Would return

```
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
```

In the example above the command is searching for the word "vistas" in the directory `written_2/` and returns all the files with the word in it. This is useful because it allows the user to check for the existence of specific contents within the entire directory at will. It can be determined if the word or pattern is relevant to any of the information in the entire directory from the command.

Running `grep -rl` `in written_2/` using the command

`$ grep -rl "vistas" written 2_/travel_guides/berlitz1`

Would return

```
written_2/travel_guides/berlitz1/IntroDublin.txt
written_2/travel_guides/berlitz1/IntroLakeDistrict.txt
written_2/travel_guides/berlitz1/IntroMadeira.txt
written_2/travel_guides/berlitz1/WhereToIbiza.txt
written_2/travel_guides/berlitz1/WhereToIsrael.txt
written_2/travel_guides/berlitz1/WhereToJerusalem.txt
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhereToMadeira.txt
```

In this new command the search for the word vista is narrowed into the `berlitz1` directory within travel guides. The command therefore allows the user to search subdirectories for relevant or irrelavant information within it to assess content of specific files rather than the entire directory at once. The command returns whch files within `berlitz` have the word "vista," making the printed output much more manageable and specific to the directory.

## grep -rc

The command `grep rc` recursively searches files for a pattern and returns the count of lines with that pattern. The `-r` aspect triggers the recursion, while the `-c` is responsible for listing the count. Running the command returns the count of lines with the target word specified. The command is written as `grep -rc "<target_word>" <file_path>`. To learn directly about `grep -rc` you can read [this source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) that I referenced.

Running `grep -rc` `in written_2/` using the command

`$ grep -rc "vistas" written_2/travel_guides/berlitz1`

Would return

```
written_2/travel_guides/berlitz1/HandRHawaii.txt:0
written_2/travel_guides/berlitz1/HandRHongKong.txt:0
written_2/travel_guides/berlitz1/HandRIbiza.txt:0
written_2/travel_guides/berlitz1/HandRIsrael.txt:0
written_2/travel_guides/berlitz1/HandRIstanbul.txt:0
written_2/travel_guides/berlitz1/HandRJamaica.txt:0
written_2/travel_guides/berlitz1/HandRJerusalem.txt:0
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt:0
written_2/travel_guides/berlitz1/HandRLasVegas.txt:0
written_2/travel_guides/berlitz1/HandRLisbon.txt:0
written_2/travel_guides/berlitz1/HandRLosAngeles.txt:0
written_2/travel_guides/berlitz1/HandRMadeira.txt:0
written_2/travel_guides/berlitz1/HandRMadrid.txt:0
written_2/travel_guides/berlitz1/HandRMallorca.txt:0
written_2/travel_guides/berlitz1/HistoryDublin.txt:0
written_2/travel_guides/berlitz1/HistoryEdinburgh.txt:0
written_2/travel_guides/berlitz1/HistoryEgypt.txt:0
written_2/travel_guides/berlitz1/HistoryFrance.txt:0
written_2/travel_guides/berlitz1/HistoryFWI.txt:0
written_2/travel_guides/berlitz1/HistoryGreek.txt:0
written_2/travel_guides/berlitz1/HistoryHawaii.txt:0
written_2/travel_guides/berlitz1/HistoryHongKong.txt:0
written_2/travel_guides/berlitz1/HistoryIbiza.txt:0
written_2/travel_guides/berlitz1/HistoryIndia.txt:0
written_2/travel_guides/berlitz1/HistoryIsrael.txt:0
written_2/travel_guides/berlitz1/HistoryIstanbul.txt:0
written_2/travel_guides/berlitz1/HistoryItaly.txt:0
written_2/travel_guides/berlitz1/HistoryJamaica.txt:0
written_2/travel_guides/berlitz1/HistoryJapan.txt:0
written_2/travel_guides/berlitz1/HistoryJerusalem.txt:0
written_2/travel_guides/berlitz1/HistoryLakeDistrict.txt:0
written_2/travel_guides/berlitz1/HistoryLasVegas.txt:0
written_2/travel_guides/berlitz1/HistoryMadeira.txt:0
written_2/travel_guides/berlitz1/HistoryMadrid.txt:0
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:0
written_2/travel_guides/berlitz1/HistoryMallorca.txt:0
written_2/travel_guides/berlitz1/IntroDublin.txt:1
written_2/travel_guides/berlitz1/IntroEdinburgh.txt:0
written_2/travel_guides/berlitz1/IntroEgypt.txt:0
written_2/travel_guides/berlitz1/IntroFrance.txt:0
written_2/travel_guides/berlitz1/IntroFWI.txt:0
written_2/travel_guides/berlitz1/IntroGreek.txt:0
written_2/travel_guides/berlitz1/IntroHongKong.txt:0
written_2/travel_guides/berlitz1/IntroIbiza.txt:0
written_2/travel_guides/berlitz1/IntroIndia.txt:0
written_2/travel_guides/berlitz1/IntroIsrael.txt:0
written_2/travel_guides/berlitz1/IntroIstanbul.txt:0
written_2/travel_guides/berlitz1/IntroItaly.txt:0
written_2/travel_guides/berlitz1/IntroJamaica.txt:0
written_2/travel_guides/berlitz1/IntroJapan.txt:0
written_2/travel_guides/berlitz1/IntroJerusalem.txt:0
written_2/travel_guides/berlitz1/IntroLakeDistrict.txt:1
written_2/travel_guides/berlitz1/IntroLasVegas.txt:0
written_2/travel_guides/berlitz1/IntroLosAngeles.txt:0
written_2/travel_guides/berlitz1/IntroMadeira.txt:1
written_2/travel_guides/berlitz1/IntroMadrid.txt:0
written_2/travel_guides/berlitz1/IntroMalaysia.txt:0
written_2/travel_guides/berlitz1/IntroMallorca.txt:0
written_2/travel_guides/berlitz1/JungleMalaysia.txt:0
written_2/travel_guides/berlitz1/WhatToDublin.txt:0
written_2/travel_guides/berlitz1/WhatToEdinburgh.txt:0
written_2/travel_guides/berlitz1/WhatToEgypt.txt:0
written_2/travel_guides/berlitz1/WhatToFrance.txt:0
written_2/travel_guides/berlitz1/WhatToFWI.txt:0
written_2/travel_guides/berlitz1/WhatToGreek.txt:0
written_2/travel_guides/berlitz1/WhatToHawaii.txt:0
written_2/travel_guides/berlitz1/WhatToHongKong.txt:0
written_2/travel_guides/berlitz1/WhatToIbiza.txt:0
written_2/travel_guides/berlitz1/WhatToIndia.txt:0
written_2/travel_guides/berlitz1/WhatToIsrael.txt:0
written_2/travel_guides/berlitz1/WhatToIstanbul.txt:0
written_2/travel_guides/berlitz1/WhatToItaly.txt:0
written_2/travel_guides/berlitz1/WhatToJamaica.txt:0
written_2/travel_guides/berlitz1/WhatToJapan.txt:0
written_2/travel_guides/berlitz1/WhatToLakeDistrict.txt:0
written_2/travel_guides/berlitz1/WhatToLasVegas.txt:0
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt:0
written_2/travel_guides/berlitz1/WhatToMadeira.txt:0
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:0
written_2/travel_guides/berlitz1/WhatToMallorca.txt:0
written_2/travel_guides/berlitz1/WhereToDublin.txt:0
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt:0
written_2/travel_guides/berlitz1/WhereToEgypt.txt:0
written_2/travel_guides/berlitz1/WhereToFrance.txt:0
written_2/travel_guides/berlitz1/WhereToFWI.txt:0
written_2/travel_guides/berlitz1/WhereToGreek.txt:0
written_2/travel_guides/berlitz1/WhereToHawaii.txt:0
written_2/travel_guides/berlitz1/WhereToHongKong.txt:0
written_2/travel_guides/berlitz1/WhereToIbiza.txt:2
written_2/travel_guides/berlitz1/WhereToIndia.txt:0
written_2/travel_guides/berlitz1/WhereToIsrael.txt:1
written_2/travel_guides/berlitz1/WhereToIstanbul.txt:0
written_2/travel_guides/berlitz1/WhereToItaly.txt:0
written_2/travel_guides/berlitz1/WhereToJapan.txt:0
written_2/travel_guides/berlitz1/WhereToJerusalem.txt:2
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt:1
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:0
written_2/travel_guides/berlitz1/WhereToMadeira.txt:1
written_2/travel_guides/berlitz1/WhereToMadrid.txt:0
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:0
written_2/travel_guides/berlitz1/WhereToMallorca.txt:0
```

In the command, the use searches the entire `berlitz1` directory for the word "vistas" and receives a count of "vistas" for every one of its file. The command shows its presence and non-presence in every file making it easy for the user to locate where certain key phrases are and aren't within a specific directory.

Running `grep -rc` `in written_2/` using the command

`$ grep -rc "vistas" written_2/travel_guides/berlitz2/Vallarta*`

Would return

```
written_2/travel_guides/berlitz2/Vallarta-History.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:1
```

In the above example, the command searches for "vistas" again but this time searches within a file pattern within the directory `berlitz2`. It allows the user to search within files titled `Vallarta` giving the user much more control over how specific they need to search for the gievn key word. The command gives a count indicating the words presence in every file that matches the pattern and path specified in the command.

## grep -rw

The command `grep rw` recursively searches for a targeted word and returns all lines with that entire word. The `-r` aspect triggers the recursion, while the `-w` functions to find the target word and the file and line it is in. Running the command returns the files with the word and the lines of text within the files that the word is in. The command is written as `grep -rw "<target_word>" <file_path>`. To learn directly about `grep -rw` you can read [this source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) which I referenced.

Running `grep -rw` `in written_2/` using the command

`$ grep -rw "Chronicles" written_2/`

Would return 

```
written_2/travel_guides/berlitz1/HistoryJapan.txt:        (“Chronicles of Japan”), the islands of Japan were born of a marriage
written_2/travel_guides/berlitz1/HistoryJapan.txt:        Prehistory and Early Chronicles
written_2/travel_guides/berlitz1/WhereToGreek.txt:        Parian Chronicles, a history of ancient Greece enscribed on marble
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt:The Ajuntament, or Casa de la Ciutat, across the plaza has held Barcelona’s city hall since 1372. It was here that the Consell de Cent, a council of 100 notable citizens, met to deal with civic affairs under the watchful eyes of the king. The original entrance can be seen around the left corner of the building, on the carrer de la Ciutat. Inside, the left staircase leads to the upper gallery of the old courtyard and to the Saló de Cent (Hall of the One Hundred). Its high ceiling resembles the barrel-vault of the Saló del Tinell, and was built at about the same time in the 14th century. The red-and-yellow bars of Catalonia’s flag decorate the walls. The hall where the city council now meets adjoins, and at the head of the black marble staircase is the Saló de les Cròniques (Hall of the Chronicles), noted for the modern murals in sepia tones by Josep Maria Sert.
```

The above command searches within the entirety of the `written_2/` directory for the key word "chronicles" within it. The command provides the lines in which "chronicles" exists in the files of the directory allowing the user to identify exactly where in each file's text the key word lies.

Running `grep -rw` `in written_2/` using the command

`$ grep -rw "Chronicles" written_2/travel_guides/berlitz1/History*`

Would return 

```
written_2/travel_guides/berlitz1/HistoryJapan.txt:        (“Chronicles of Japan”), the islands of Japan were born of a marriage
written_2/travel_guides/berlitz1/HistoryJapan.txt:        Prehistory and Early Chronicles
```

The example command searches within all files titled with "History" within the `written_2/travel_guides/berlitz1/` directory for the key word "chronicles." The command once again provides the lines in which "chronicles" exists in the files with the "History" pattern in the aforementioned directory, allowing the user to precisely narrow down to specific texts which lines the key word lies.

## grep -rn

The command `grep rn` recursively searches for a targeted word and returns a numbered list of all lines with that word. The `-r` is responsible for the recursion, while the `-n` functions to find the target word, its files and lines. Running the command returns the lines and line numbers where the target word is found in the file. The command is written as `grep -rn "<target_word>" <file_path>`. To learn about `grep -rn` you can read [this source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) that I used as a reference.

Running `grep -rn` `in written_2/` using the command

`$ grep -rn "Chronicles" written_2/travel_guides/berlitz1/History*`

Would return 

```
written_2/travel_guides/berlitz1/HistoryJapan.txt:9:        (“Chronicles of Japan”), the islands of Japan were born of a marriage
written_2/travel_guides/berlitz1/HistoryJapan.txt:23:        Prehistory and Early Chronicles
```

This example command searches the same pattern and directory as the previous `rw` one does. It finds all files titled "History" within the `written_2/travel_guides/berlitz1/` directory for the key word "chronicles." However, since it is usign `rn` the command not only prints the lines in which "chronicles" exists, but also prints exactly what line numbers they exist at. This allows the user to still search specific texts while also obtaining more relevant information on the key word's whereabouts that would increase their search efficiency.

Running `grep -rn` `in written_2/` using the command

`$ grep -rn "great pioneering skill" written_2/`

Would return 

```
written_2/travel_guides/berlitz2/Canada-History.txt:25:With great pioneering skill, Upper Canada’s first lieutenant governor, John Simcoe, pushed new highways north from Lake Ontario and west to Hamilton. He established the provincial capital at a trading post, Toronto, in the heart of a malarial swamp, and renamed it York. A landed gentry made up of army officers, government officials, and commercial speculators ran the province, creating a hereditary aristocracy known as the Family Compact. More Americans were lured over the border with land grants; the population rose from 14,000 in 1792 to 90,000 by 1812. French-Canadians were also multiplying rapidly, from 60,000 when New France was abandoned in 1760 to 330,000 fifty years later.
```

This final example command searches the entire `written_2/` directory. It prints out the line number of every line in the entire directory with the phrase "great pioneering skill." This command provides great use because it accesses all information in the directory to provide the pattern's location giving a more wholistic view of the directory. It uses a more complex phrase to search for exemplifying that searches aren't limited to single words or simple patterns and still successfully numbers where the target phrase can by displaying its line number in its file path.
