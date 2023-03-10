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

## less -N

The command `less -N` searches for a targeted file and returns its contents in a parsable manner, but with a column for the line numbers of contents. The command is written as `less -N <file_path>`. To learn directly about `less -N` you can read [this source](https://phoenixnap.com/kb/less-command-in-linux) which I referenced.

Running `less -N` in `written_2/` using the command

`$ less -N written_2/travel_guides/berlitz1/HandRHawaii.txt`

Would return 

```
1
2
3
4
5
6         Oahu (Including Honolulu)
7         Aston Waikiki Sunset $$$ 229 Paoakalani Avenue, Honolulu, HI
8         96815; Tel. (808) 922-2700 or (800) 336-5599; fax (808) 922-8785;
9         <www.aston-hotels.com>. One of Aston’s many condominium resort
10         properties, this modern high-rise has large rooms with complete
11         kitchens. Lanais afford views of the Diamond Head end of Waikiki Beach.
12         410 rooms.
13         Halekulani $$$$ 2199 Kalia Road, Honolulu, HI 96815; Tel.
14         (808) 923-2311 or (800) 367-2343; fax (808) 926-8004;
15         <www.halekulani.com>. Very large rooms, most facing the ocean,
```

The above command searches within the`written_2/travel_guides/berlitz1/HandRHawaii.txt` text file and provides the first few lines within it, numbering each of those lines even as they are parsed. This gives insight to the locaiton of contents in a file that allows the user to better track where critical information is within it so they can more effectievly search for and track down information in the file.

Running `less -N` in `written_2/` using the command

`$ less -N written_2/travel_guides/berlitz1/HandRHongKong.txt`

Would return, after using the down arrow until the file stopped parsing,

```
15         arrangements, the Hong Kong Hotel Reservation Center at the
16         International Airport will be happy to arrange accommodations for you
17         on your arrival.
18         As a basic guide, the symbols below have been used to
19         indicate high-season rates in Hong Kong dollars, based on double
20         occupancy, with bath or shower. Unless otherwise noted, hotels take all
21         major credit cards. A 10% service charge and 5% government tax will be
22         added to the bill.
23         $$$$above HK$2,500
24         $$$HK$l,600 to HK$2,500
25         $$HK$950 to HK$1,600
26         $below HK$950
27
28
29
```

The above command searches within the`written_2/travel_guides/berlitz1/HandRHongKong.txt` text file and provides, after parsing downwards as far as possible, the last remaining lines within it, numbering each of those lines even as they are parsed. This example represents how the insight provided by this command, as previously aforementioned, spans the entire file as it can clearly be seen that the numbering is consistent for ever line, including blank space, until the end of the file. It shows that the `less` command functionality specified when first typed in the terminal is consistent throughout the entire file.

## less -M

The command `less -M` allows parsing of the specified file, but provides more information about each line as they are being parsed. It provides the file path of the file being parsed, the line numbers being shown and the percentage of the file that has been shown by the command at the line the user is at. The command is written as `less -M <file_path>`. To learn about `less -M` you can read [this source](https://phoenixnap.com/kb/less-command-in-linux) that I used as a reference.

Running `less -M` in `written_2/` using the command

`$ less -M written_2/travel_guides/berlitz1/HandRHongKong.txt`

Would return 

```
        Recommended Hotels
        Hong Kong has some of the most luxurious hotels in the
        world, with representatives from all the major international chains.
        Hotels listed below have full air-conditioning, offer 24-hour or
        limited room service, and a wide range of facilities. Hong Kong hotels
        have excellent business services and conference facilities; many have
        shopping malls.
        Reservations are strongly recommended, particularly in
        summer and at Christmas. If you do arrive without making advance
        arrangements, the Hong Kong Hotel Reservation Center at the
written_2/travel_guides/berlitz1/HandRHongKong.txt lines 1-15/29 54%
```

This example command shows how the command provides the normal `less` functionality while providing crucial information at the end of the terminal that updates in real time as the user parses through the file. It shows the user where in the file they are at with line numbers, how much of they file they have explored or have left with the percentage of file covered indicator as well as reminding them what file they are parsing by displaying its full path in the terminal. It is useful to help the user keep track of what they are parsing, where they are parsing and how much of it they have parsed at the line they are at during any given time.

Running `less -M` in `written_2/` using the command

`$ less -M written_2/travel_guides/berlitz1/HandRHongKong.txt`

Would return, after parsing one less than as far down as possible using the down arrow,

```
        Breakfast included. 11 rooms.
        Lodge at Koele $$$$ P.O. Box 310, Lanai City, HI 96793;
        Tel. (808) 565-7300 or (800) 321-4666; fax (808) 565-4561;
        <www.lanai-resorts.com>. Lanai’s upcountry, very upscale resort
        is appointed like an Old English estate, with writing desks,
        four-poster beds, library, music room. The 21-acre grounds include a
        croquet court, lawn bowling, horseback-riding stables, formal gardens,
        and a world-class golf course. 102 rooms.
        Manele Bay Hotel $$$$ P.O. Box 310, Lanai City, HI 96793;
        Tel. (808) 565-7700 or (800) 321-4666; fax (808) 565-2483;
        <www.lanai-resorts.com>. A full-service, quite plush resort on
        Lanai’s finest beach (Hulopoe), the Manele Bay Hotel offers water
        sports, golf, tennis, a spa, and jeep tours. 250 rooms.


written_2/travel_guides/berlitz1/HandRHawaii.txt lines 233-247/248 100%
```

This final example command shows how the command provides the normal `less` functionality while providing crucial information at the end of the terminal throughout the entire file. It shows what the command looks like after parsing to 100% of the file and reveals that the command does update the percentage throughout the file, provide what the final lines are while still showing the file path. This command exemplifies the functionality of `-M` is not lost while parsing throughout the file and reveals that crucial information about the files ending can be found by using this command and parsing to that location.
