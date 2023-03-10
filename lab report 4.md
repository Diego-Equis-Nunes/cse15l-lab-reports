# Lab Report 4

## "Done Quick"

In week 7 of lab we were tasked to complete multiple steps to clone, commit and push files of a repository to github as fast as possible. There was a brief section of setup including removal of the need to use our password to log into our CSE 15L accounts, as well as setup for the repository we were going to manipulate. Repository setup consisted of forking the repository into our personal acocunts and making sure any clones of that repository in our IDE were removed. After all setup, we were required to do the following steps, described exactly as they are in [Lab Report 7](https://ucsd-cse15l-w23.github.io/week/week7/), as fast as possible:

1. Log into ieng6
2. Clone your fork of the repository from your Github account
3. Run the tests, demonstrating that they fail
4. Edit the code file to fix the failing test
5. Run the tests, demonstrating that they now succeed
6. Commit and push the resulting change to your Github account

## My Reproduction of Step 1 - Logging in

![Image](Step4LogIn.png)

Keys Pressed
* `<up>`
* `<enter>`

The command `ssh cs15lwi23aoj@ieng6.ucsd.edu` was 1st up in my device's search history, so I used the up arrow to access it and hit `<enter>` to run it. The command itself logged me into my student specific CSE 15L account for the school's servers.

## My Reproduction of Step 2 - Cloning

![Image](Step5CloneFork.png)

Keys Pressed
* `<up>`
  * Was pressed 14 times
* `<enter>`

The command `git clone git@github.com:Diego-Equis-Nunes/lab7.git` was 14th up on my account's search history when on the server, so I used the up arrow to access it and hit `<enter>` to run it. This command cloned the repository `lab7` from my Github account onto the my accounts files in the server.

## My Reproduction of Step 3 - Test Failure

![Image](Step6TestsFail.png)

Keys Pressed

*  `cd<space>lab7`
*  `<enter>`
*  `<up>`
  * Was pressed 11 times
* `<enter>`
* `<up>`
  * Was pressed 11 times
* `<enter>`

To run the proper JUnit tests on the proper java file, I had to change into the `lab7` directory I created from the forked repository I used during the setup phase. I typed the characters `cd`, `<space>` and `lab7` consecutively then hit `<enter>` to change directories into `lab7`. After doing so, I was in the right directory to start running tests. The command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` was 11th up on my account's search history when on the server, so I used the up arrow to access it and hit `<enter>` to run it. Running this command compiled all java files my CSE 15L account has on the `ieng6` server. Right after, I used the up arrow 11 times to access the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` that was 11th in my history after using the previous command. I used `<enter>` to run it, which caused the file I specified in the command `ListExamplesTests.java` to be run. This file hade JUnit tests for the file that tested the file `ListExamples.java` and showed that one of the tests failed.

## My Reproduction of Step 4 - Debugging

> Bugged file `ListExamples.java`

![Image](Step7UnfixedFull.png)

> Error in code of file `ListExamples.java`

![Image](Step7UnfixedZoom.png)

> Debugged file `ListExamples.java`

![Image](Step7FixedFull.png)

> Fixed code of file `ListExamples.java`

![Image](Step7FixedZoom.png)

Keys Pressed
* `<up>`
  * Was pressed 14 times
* `<enter>`
* `<^O>`
* `<enter>`
* `<down>`
  * Was pressed 42 times
* `<right>`
  * Was pressed 12 times
* `<backspace>`
* `2`
* `<^X>`
* `y`
* `<enter>`

The command `nano ListExamples.java` was 14th up on my account's search history when on the server, so I used the up arrow to access it and hit `<enter>` to run it. Running this command allowed a visual representation of the file `ListExamples.java` that I specified, with multiple different options on how to interact with it present on the terminal. For example, I hit `<^O>` as the terminal showed and hit `<enter>` to be able to directly edit the file's text. I then used the down arrow 42 times and the right arrow 12 times to reach the error in the code of `ListExamples.java` that previously failed the JUnit tests. As shown in the images, the code in the file was iterating `index1` instead of `index2` in the for loop meant to iterate `index2`. As a result, once I was on the character `1` of `index1` to `index2` by pressing `<backspace>` to delete `1` and then pressed `2` to replace it. After, I pressed `<^X>` to exit the file, hit `y` to accept the prompt asking if I wanted to save my changes and hit `<enter>` to then exit the screen the `nano` command put me in within the terminal. These set of steps successfully allowed me to change the code that was failing the JUNit tests to now pass.

## My Reproduction of Step 5 - Test Success

![Image](Step8TestsPass.png)

Keys Pressed
* `<up>`
  * Was pressed 3 times
* `<enter>`
* `<up>`
  * Was pressed 3 times
* `<enter>`

After previously running the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` it was only 3rd up on my account's search history on the server when I used the up arrow to access it. After hitting `<enter>` to run it and compile all java files my CSE 15L account has on the `ieng6` server, I used the up arrow 3 times to access the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` since it was 3rd in my history after using the previous command. I hit `<enter>` to run it, causing the file `ListExamplesTests.java` that I specified in the command to be run. This file hade JUnit tests for the file `ListExamples.java` I recently debugged and showed that all of the tests now passed.

## My Reproduction of Step 6 - Commit and Push

![Image](Step9CommitPush.png)

Keys Pressed
* `<up>`
  * Was pressed 14 times
* `<enter>`
* `<up>`
  * Was pressed 14 times
* `<enter>`
* `<up>`
  * Was pressed 14 times
* `<enter>`
* `<up>`
  * Was pressed 14 times
* `<enter>`
* `cd<space><~>`
* `<enter>`
* `rm<space><->rf<space>lab7`
* `<enter>`
* `exit`
* `<enter>`

Finally, I began the set of commands I needed to commit and push my changes to my Github repository. I hit the up arrow 14 times to access the 14th command in my account's history, which was `git add ListExamplesTests.java ListExamples.java`. I hit `<enter>` so that this command added the files `ListExamplesTests.java` and `ListExamples.java` to the files I wanted to commit to the Github. After, I hit the up arrow 14 more times to access the now 14th command in the history, which was the command following the previous one before I reused it. This command was `git commit -m "Done"` and after hitting `<enter>` it added the message "Done" as the message to be committed once I push all changes to Github. To actually commit the changes to Github, I used the up arrow 14 times to access the command `git commit` and hit `<enter>` to run it. Once I successfully committed the changes, I pushed them to my Github repository by using the up arrow 14 times to access the command `git push` and hit `<enter>` to run it. Doing this series of steps caused all my changes to be properly pushed to my Github repository. Since this was a timed set of commands we used in lab to compete in for multiple rounds, I also took the liberty of resetting my files so I could practice and run these commands in the same order once again. To do so, I removed the files I cloned by changing my directory out of `lab7` by typing the `cd`, `<space>`, and `<~>` in the same line then `<enter>` to complete the command exiting out of the `lab7` directory. Immediately after I removed the files by typing `rm`, `<space>`, `<->`, `rf`, `<space>`, and `lab7` then `<enter>` to run the command I was able to type `exit` and hit `<enter>` to run the command that logged me out of my CSE 15L account on the `ieng6` server. After all that, all that was left to do to fully reset the repository was to remove it from delete it from my Github account so I could reclone it when practicing again. This would be done from Github, however, so everything we need to run in terms of commands from the terminal is complete.
