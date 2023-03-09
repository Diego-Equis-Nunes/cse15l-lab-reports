# Lab Report 5

# Researching Commands Once Again

The command `find` is used to list files and directories in the directory path that is taken as an argument. This document will be exploring examples of different command line options for the `find` command to achieve different results. The folder `written_2/` will be searched through using the various `find` commands present. 

## grep -rl

The command `grep -rl` is a quick way to recursively search files for a line. The `-r` aspect does the recursion, while the `-l` is responsible for listing file names. The function of recursion is to call on itself to work through different lists of files or directories. So when `grep -rl` is run, the recursive aspect is that the command would call itself on the specified directory and within that call itself again to look at any directory or file within it. Those calls then call themselves again to search driectories and files within them, so on and so forth. As a result, running the command returns all files with the target word specified. It is different from `grep -l` because without the recursive aspect, `grep -l` needs a file path to a directory with files in it to run properly. Using `grep -l` explores the file path to files specified, while `grep -rl` can be used on a directory to iterate through everything in it to find a specific pattern in a broader scope of files at one time.  The command is written as `grep -rl "<target_word>" <file_path>` and searches for the target word in the specified file path and returns all files with the word. To read directly about `grep -rl` you can read [this article](https://alvinalexander.com/linux-unix/recursive-grep-r-searching-egrep-find/#:~:text=grep%20%2Drl%20alvin%20.,i%20for%20case%2Dinsensitive%20searches) with all the details.

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

In the example above the command is searching for the word "vistas" in the directory `written_2/` and returns all the files with the word in it. This is useful because it allows the user to check for the existence of specific contents within the entire directory at will. Since we are using `grep -rl` instead of `grep -l` this is possible because the recursive aspect of the command allows us to search a directory and allow the recursion to locate `.txt` files without the user needing to specify the file path to each `.txt` shown in the results. It can be determined if the word or pattern is relevant to any of the information in the entire directory from the single command.

Running `grep -rl` in `written_2/` using the command

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

In this new command the search for the word "vista" is narrowed into the `berlitz1` directory within `travel_guides`. It is useful to note `grep -l` could have been used to achieve the same results in this case it `/*.txt` was added to the end of the command to search for `.txt` files within the directory. This is only because   `berlitz1` is a directory with files directly after it and not just storing directories. In this case `grep -rl` is useful because when we want to search in a set of directories but do not want to worry about the location of the files specifically because the recursive aspect of the function handles that for us. This example of command still allows the user to search subdirectories for relevant or irrelavant information to assess content of specific files, rather than the entire directory as shown previously. The command returns which files within `berlitz1` have the word "vista," making the printed output much more manageable and specific to the directory.

## grep -rc

The command `grep -rc` recursively searches files for a pattern and returns the count of lines with that pattern. The `-r` aspect triggers the recursion, which works exactly as desribed in the explanation for `grep -rl` as shown above, while the `-c` is responsible for listing the count. Running the command returns the count of lines with the target word specified. The command is written as `grep -rc "<target_word>" <file_path>`. To learn directly about `grep -rc` you can read [this source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) that I referenced.

Running `grep -rc` in `written_2/` using the command

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

In the command, the user searches the entire `berlitz1` directory for the word "vistas" and receives a count of "vistas" for every one of its file. The command shows its presence and non-presence in every file making it easy for the user to locate where certain key phrases are and aren't within a specific directory. It's especially helpful to add the recursive aspect to this command because otherwise, using `grep -c` alone would require a filepath to a directory with `.txt` files within it. By adding `grep -r` into the mix, we are able to search an entire directory because the recursion identifies the filepaths to each `.txt` file for us. Regardless of the approach, it is the `grep -c` aspect that takes the file path given and displays the amount of times the pattern specified is matched within the file. 

Running `grep -rc` in `written_2/` using the command

`$ grep -rc "vistas" written_2/travel_guides/berlitz2/Vallarta*`

Would return

```
written_2/travel_guides/berlitz2/Vallarta-History.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:1
```

In the above example, the command searches for "vistas" again but this time searches within a file pattern within the directory `berlitz2`. It allows the user to search within `.txt` files titled `Vallarta` giving the user much more control over how specific they need to search for the given key word. The command gives a count indicating the word's presence in every file that matches the pattern and path specified in the command. In this example, `grep -rc` and `grep -c` don't differ much in effectiveness because the user has a specific path they need to gather information from. However, it does show that `grep -rc` still has the capability to be as specific as searching a specific single directory path leading directly to `.txt` files on top of being able to search entire directories without detailed specification of file location. It also worth noting that without recursion `Vallarta*` would not work at the end of the command just using `-c` and instead searching for `.txt` files using `*.txt` at the end of the file path would be necessary. So even though both `-rc` and `-c` can search for specific pathing, `-rc` still gives more freedom in that regard. Regardless of the approach, it is still the `grep -c` aspect taking the given file path and searching for the count of the specified pattern within the files.

## grep -w

The command `grep -w` searches for a targeted word, returns the files with it and returns all lines of those files with that entire word. The `-w` functions to find the target word and line the keyword is in, while the file pathing specified indicates which files it should search for that information. Running the command returns the files with the word and the lines of text, within said files, that the word is in. The command is written as `grep -w "<target_word>" <file_path>`. To learn directly about `grep -w` you can read [this source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) which I referenced.

Running `grep -w` in `written_2/` using the command

`$ grep -w "Chronicles" written_2/travel_guides/berlitz1/*.txt`

Would return 

```
written_2/travel_guides/berlitz1/HistoryJapan.txt:        (“Chronicles of Japan”), the islands of Japan were born of a marriage
written_2/travel_guides/berlitz1/HistoryJapan.txt:        Prehistory and Early Chronicles
written_2/travel_guides/berlitz1/WhereToGreek.txt:        Parian Chronicles, a history of ancient Greece enscribed on marble
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt:The Ajuntament, or Casa de la Ciutat, across the plaza has held Barcelona’s city hall since 1372. It was here that the Consell de Cent, a council of 100 notable citizens, met to deal with civic affairs under the watchful eyes of the king. The original entrance can be seen around the left corner of the building, on the carrer de la Ciutat. Inside, the left staircase leads to the upper gallery of the old courtyard and to the Saló de Cent (Hall of the One Hundred). Its high ceiling resembles the barrel-vault of the Saló del Tinell, and was built at about the same time in the 14th century. The red-and-yellow bars of Catalonia’s flag decorate the walls. The hall where the city council now meets adjoins, and at the head of the black marble staircase is the Saló de les Cròniques (Hall of the Chronicles), noted for the modern murals in sepia tones by Josep Maria Sert.
```

The above command searches within the entirety of the `written_2/travel_guides/berlitz1/` directory in its `.txt` files for a the pattern "Chronicles" if it is matched as a whole word. The command provides the lines in which "Chronicles" exists in the files of the directory, allowing the user to identify exactly where in each file's text the key word lies. This gives meaningful insight to the contents of a file as well as where information is stored about a particular pattern within a directory.

Running `grep -w` in `written_2/` using the command

`$ grep -w "If a retail customer" written_2/non-fiction/OUP/Abernathy/*.txt`

Would return 

```

written_2/non-fiction/OUP/Abernathy/ch9.txt:The possibility of mass customization for some apparel items presents another market opportunity that demands short-cycle production. If a retail customer pays a premium for a custom pair of jeans, dress shirt, or suit, that customer will expect the item to be delivered to her home within days, not weeks or months. We are a nation of last-minute shoppers, and mass customization will have to compete against overnight delivery of apparel items with less than perfect fit from a specialty catalog company. Speed of delivery has increasingly become part of the competitive equation.
```

The example command searches within all `.txt` files of the `written_2/travel_guides/berlitz1/` directory for the pattern "If a retail customer" as a word. The command provides that you can search for a phrase or even sentence within a file and are not just restricted to single words to find information while using the `-w` command. It shows both the file the phrase was found and the lines it appears in, giving insight as to where in the directory and where in the file the specific information someone is looking for resides.

## grep -n

The command `grep -n` recursively searches for a targeted word and returns a numbered list of all lines with that word. The `-n` functions to find the target word, its lines, while file pathing specifies the file or files to search that information for. Running the command returns the lines and line numbers where the target word is found in the file. The command is written as `grep -n "<target_word>" <file_path>`. To learn about `grep -n` you can read [this source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) that I used as a reference.

Running `grep -n` in `written_2/` using the command

`$ grep -n "Chronicles" written_2/travel_guides/berlitz1/*.txt`

Would return 

```
written_2/travel_guides/berlitz1/HistoryJapan.txt:9:        (“Chronicles of Japan”), the islands of Japan were born of a marriage
written_2/travel_guides/berlitz1/HistoryJapan.txt:23:        Prehistory and Early Chronicles
written_2/travel_guides/berlitz1/WhereToGreek.txt:352:        Parian Chronicles, a history of ancient Greece enscribed on marble
```

This example command searches similarily how the `-w` one does. Due to the file pathing, it finds all `.txt` files within the `written_2/travel_guides/berlitz1/` directory for the key word "Chronicles." However, since it is using `-n` the command not only prints the lines in which "Chronicles" exists, but also prints exactly what line numbers they exist at. This allows the user to still search specific texts while also obtaining more relevant information on the key word's whereabouts that would increase their search efficiency.

Running `grep -n` in `written_2/` using the command

`$ grep -n "great pioneering skill" written_2/travel_guides/berlitz2/*.txt`

Would return 

```
written_2/travel_guides/berlitz2/Canada-History.txt:25:With great pioneering skill, Upper Canada’s first lieutenant governor, John Simcoe, pushed new highways north from Lake Ontario and west to Hamilton. He established the provincial capital at a trading post, Toronto, in the heart of a malarial swamp, and renamed it York. A landed gentry made up of army officers, government officials, and commercial speculators ran the province, creating a hereditary aristocracy known as the Family Compact. More Americans were lured over the border with land grants; the population rose from 14,000 in 1792 to 90,000 by 1812. French-Canadians were also multiplying rapidly, from 60,000 when New France was abandoned in 1760 to 330,000 fifty years later.
```

This final example command searches the entire `written_2/travel_guides/berlitz2/*.txt` directory for `.txt` files. It prints out the line number of every line in the entire directory with the phrase "great pioneering skill." This command is great because showcases much like `-w` that a pattern in `-n` isn't limited to a single word, but can be used to find sentences or phrases as well. It accesses all information on `.txt` files in the specified directory to provide the pattern's location and line number, as well as the filepath it was accessed from to creat easy access to it whereabouts.

