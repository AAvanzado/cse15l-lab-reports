# Lab Report 4

## Log into ieng6
![Image](SSHLogin.png)
Keys pressed: `<up>`

The `ssh cs15lwi23alh@ieng6.ucsd.edu` command was 1 up in the search history, so I used the up arrow to access it.

## Clone your fork of the repository from your Github account
![Image](gitCloneCD.png)
Keys pressed: `<up>`(x11), `<enter>`, `cd l<tab><enter>`

The `git clone git@github.com:AAvanzado/lab7.git` command was 11 up in the search history, so I used the up arrow to access it. For `cd lab7/`, I typed in "cd l" and used the auto-complete <tab> to finish the command.

## Run the tests, demonstrating that they fail
![Image](TestFailures.png)
Keys pressed: `<up>`(x8) `<enter>`, `<up>`(x8) `<enter>`

The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was 8 up in the search history, so I used the up arrow to access it. The same was the case for the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples`.

## Edit the code file to fix the failing test
![Image](nanoCMD.png)
![Image](nanoEdits.png)
Keys pressed: `<up>`(x8), `*touch pad to scroll*`, `<right>`(x12), `<backspace> 2`, `<Ctrl+O><enter><Ctrl+X>`

The `nano ListExamples.java` command was 8 up in the search history, so I used the up arrow to access it. For editing the file in nano, I used the touch pad on my mac to scroll down to the line I needed to edit. Then I used the right arrow 12 times to get to the variable I needed to edit. After that, I changed the `index1` to `index2` by using `<backspace>` then 2. Finally, I saved the updates using `<Ctrl+O>`, confirmed the name of the file with `<enter>`, and exited nano with `<Ctrl+X>`. 

## Run the tests, demonstrating that they now succeed
![Image](TestPassing.png)
Keys pressed: `<up>`(x3) `<enter>`, `<up>`(x3) `<enter>`

After running the tests before, the `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was 3 up in the search history, so I used the up arrow to access it. The same was the case for the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples`.

## Commit and push the resulting change to your Github account
![Image](AddCommitPush.png)
Keys pressed: `git add L<tab>j<tab><enter>`, `git commit -m "Updated" <enter>`, `git push <enter>`

For `git add ListExamples.java` I typed "git add L" then `<tab>` to auto-complete into `git add ListExamples.`. Then, because there was both ListExamples.java and ListExamples.class, I had to enter "j" then `<tab>` to get `git add ListExamples.java`. For both `git commit -m "Updated"` and `git push` I felt like they were too high up in the history so I just typed them out without any shortcuts.
