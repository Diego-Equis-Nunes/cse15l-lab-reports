# Lab Report 5

# Researching Commands Once Again

The command `less` is used to alter terminal display and interation by causing the terminal to show the first screen of lines that would otherwise be shown and allow the user to use the arrow keys to access more lines after it to explore the file. The user can also use the space bar to go down a screen length in the file. As a result, the command runs until the user exits the file contents displayed by using pressing 'q' to exit `less` and return to the default terminal. This document will be exploring examples of different command line options for the `less` command to achieve different results. The folder `written_2/` will be searched through using the various `less` commands present. 

## less -p

The command `grep -p` is a way to display file contents at the first location a specified pattern is found in the file. The command is written as `less -p "<target_pattern>" <file_path>` which searches for the target pattern in the specified file path and displays the contents of the file within the constraint of the terminal starting at the first line with the target pattern in it. To read directly about `less -p` you can read [this article](https://phoenixnap.com/kb/less-command-in-linux) with all the details.

Running `less -p` in `written_2/` using the command

`$ less -p "vistas" written_2/travel_guides/berlitz1/HandRHawaii.txt`

Would return

```
Pattern not found (press return)
```

And then after hitting `return` would print

```
Oahu (Including Honolulu)
Aston Waikiki Sunset $$$ 229 Paoakalani Avenue, Honolulu, HI
96815; Tel. (808) 922-2700 or (800) 336-5599; fax (808) 922-8785;
<www.aston-hotels.com>. One of Aston’s many condominium resort
properties, this modern high-rise has large rooms with complete
kitchens. Lanais afford views of the Diamond Head end of Waikiki Beach.
410 rooms.
Halekulani $$$$ 2199 Kalia Road, Honolulu, HI 96815; Tel.
(808) 923-2311 or (800) 367-2343; fax (808) 926-8004;
<www.halekulani.com>. Very large rooms, most facing the ocean,
```

In the example above the command is searching for the word "vistas" in the directory `written_2/travel_guides/berlitz1/HandRHawaii.txt/` and returns the line of file including it and everything after it in the terminal display. However, in this case the pattern is not found, so the terminal indicates such and then allows the user to hit `return` to then access the file's contents from its beginning, exactly as using `less` would without adding in `-p`. This is useful because it indicates to the user whether the relevant information they are searching for exists but still allows them the functionality of `less` regardless without having to retype the command. It quickly tells the user about the information they are searching for while allowing them to still explore the files by default functionality of `less` if need be.

Running `less -p` in `written_2/` using the command

`$ less -p "Aston" written_2/travel_guides/berlitz1/HandRHawaii.txt`

Would return

```
Aston Waikiki Sunset $$$ 229 Paoakalani Avenue, Honolulu, HI
96815; Tel. (808) 922-2700 or (800) 336-5599; fax (808) 922-8785;
<www.aston-hotels.com>. One of Aston’s many condominium resort
properties, this modern high-rise has large rooms with complete
kitchens. Lanais afford views of the Diamond Head end of Waikiki Beach.
410 rooms.
Halekulani $$$$ 2199 Kalia Road, Honolulu, HI 96815; Tel.
(808) 923-2311 or (800) 367-2343; fax (808) 926-8004;
<www.halekulani.com>. Very large rooms, most facing the ocean,
```

In the example above the command is searching for the word "Astong" in the directory `written_2/travel_guides/berlitz1/HandRHawaii.txt/` and returns the line of file including it and everything after it in the terminal display. In this case the pattern is found, so the terminal prints the file contents starting at the first line the pattern is found and then allows access to the file's contents from there. The user can access previous and subsequent lines from that location. This is useful because it indicates to the user the relevant information they are searching does exist and they can more purposefully search around the information they were looking for when typing the command. It quickly directs the user to the information they are searching without them having to search a file themselves while allowing them to still explore the rest of the file by default functionality of `less` if need be.

## less -f

The command `less f` force opens files that aren't considered standard files. This means it can open things such as directories in place of a file, or even files special to the operating device. The command is written as `less -f <file_path>` where the file path doesn't have to lead to a file since this command can open directories as well. To learn directly about `less -f` you can read [this source](https://phoenixnap.com/kb/less-command-in-linux/) that I referenced.

Running `less -f` in `written_2/` using the command

`$ less -f "vistas" written_2/travel_guides/berlitz1`

Would return

```
written_2/travel_guides/berlitz1/ (END)
```

And after hitting `enter` prints

```
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
(END)
```

In the command, the user searches the `written_2/travel_guides/berlitz1/` directory. The command shows the directory is found and then shows tildes `~` because the directory doesn't have text content to display. Since `written_2/travel_guides/berlitz1/` is the pathing into a directory with only `.txt` files, the use of this command shows that when forcibly opening a directory directly connected to text files you can not access any of those contents without directly pathing to them. This command demonstrates that pathing to the directory with text files provides no valuable information about the text files to the user.

Running `less -f` in `written_2/` using the command

`$ less -f "vistas" written_2/`

Would return

```
written_2/ (END)
```

And after hitting `enter` prints

```
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
(END)
```

In the command, the user searches the `written_2/` directory. The command shows the directory is found and then shows tildes `~` because the directory doesn't have text content to display. Since `written_2/` is the pathing into a directory with only directories in it files, the use of this command shows that when forcibly opening a directory directly connected to directories you can not access any of the inner directory contents without directly pathing to their contents themselves. This command demonstrates that pathing to the directory with directories provides no valuable information about the directories the outer directory stores to the user.

## less

The command `grep -w` searches for a targeted word, returns the files with it and returns all lines of those files with that entire word. The `-w` functions to find the target word and line the keyword is in, while the file pathing specified indicates which files it should search for that information. Running the command returns the files with the word and the lines of text, within said files, that the word is in. The command is written as `grep -w "<target_word>" <file_path>`. To learn directly about `grep -w` you can read [this source](https://phoenixnap.com/kb/less-command-in-linux) which I referenced.

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

## less

The command `grep -n` recursively searches for a targeted word and returns a numbered list of all lines with that word. The `-n` functions to find the target word, its lines, while file pathing specifies the file or files to search that information for. Running the command returns the lines and line numbers where the target word is found in the file. The command is written as `grep -n "<target_word>" <file_path>`. To learn about `grep -n` you can read [this source](https://phoenixnap.com/kb/less-command-in-linux) that I used as a reference.

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

