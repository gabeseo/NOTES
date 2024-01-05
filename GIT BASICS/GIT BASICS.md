Lesson overview
This section contains a general overview of topics that you will learn in this lesson.

 * How to create a repository on GitHub.
 * How to get files to and from GitHub.
 * How to take “snapshots” of your code.

change directory commnands:
 - $ cd Desktop
 - $ cd repos : Changes directory in the current working root directory
    - Cant change between different directories by more than 1
 - $ cd : goes back to the parent directory

- F : tells ls to classify the output by adding a marker to file and directory names to indicate what they are
- touch : is to make a new file
- git add : add to online repository (still need to commit)
- git commit : push it to the online github

Creating the repo steps!
 1. Create a new repository on Github (ex. git_test) (check the README.md)
 2. Copy the SSH URL to be able to copy(clone) this repository onto your local machine
 3. On git bash, create a directory(file) using the mkdir command (ex. mkdir repo)
 4. Move to the new folder created using the cd command (ex. cd repo)
 5. Clone the repository from GitHub onto your computer using the command git clone followed by pasting the copied URL from earlier (ex. gitclone (paste))
 6. To test if you successfully connected the repo on GitHub to your local machine, you can cd into the new folder (git_test in this example) then enter git remote -v

Using the Git workflow!
 1. Create a new file in the folder (git_test) called (lorem.txt) with the command touch lorem.txt
 2. Type git status and see that the file is not staged so far
 3. Type git add lorem.txt to add your lorem.txt file to the staging area in Git (two-step process)
 4. Type git status again and see that the file is now in the staging area
 5. Type git commit -m"Add lorem.txt" and then type git status once more to see that the output now says there is nothing else to commit
 6. Type git log and you should be able to see an entry for the "Add lorem.txt" commit and the details of the author who just made the commit
   - If your terminal is stuck in a screen with (END) at the bottom, press q to escape

Modify a file or two
 1. Open VScode and open the README.md file by typing code . inside the repository
 2. Modify the README.md file and save with Ctrl + S
 3. Press Ctrl + ` to open the terminal and type git status and see that the README.md is shown as not staged or committed
 4. Add README.md to the staging area with git add README.md
   - git status should say in green the README.md file is now added to the staging area
 5. Open lorem.txt, modify it, save it, stage it, use git add. cmd to all all files into the current directory and all subsequent directories to the staging area and then type in git status once more to see that everything is now in the staging area
 6. Commit all the files in the staging area and add a commit msg. git commit -m"Edit README.md and lorem.txt" then type git status to see that there is nothing to commit now
 7. Type in git log to see that there are now three entries

Push your work to GitHub
 1. Type git push (or git push origin main)
 2. Type git status and it should output that there is nothing to commit
 3. If you reload the repository on GitHub, there should be a README.md and lorem.txt files that you just pushed from your local machine

CHEATSHEET
 - Reference list of the most commonly used Git commands
  1. Commands related to a remote repository
   * git clone git@github.com:USER-NAME/REPOSITORY-NAME.git
   * git push or git push origin main
  2. Commands related to the workflow
   * git add .
   * git commit -m"Message describing what you did"
  3. Commands related to checking status or log history
   * git status 
   * git log
 - Basic Git syntax is program | action | destination 
  - For example: 
   - git add. is read as git | add | . , where the period represents everything in the current directory
   - git commit -m"msg" is read as git |commit -m | "msg 
   - git status is read as git | status | (no destination)

Git best practices
 - Two helpful best practices to consider are atomic commits and leveraging those atomic commits to make your commit messages more useful to future collaborators
  - An atomic commit is a commit that includes changes related to only one feature or task of your program. Two main reasons for doing this:
   1. If something you change causes problems, it is easy to revery the specific change
   2. Enables you to write better commit messages

Changing the Git commit message editor
 - There is a way to ensure that if you use git commit without hte message flag (-m), you won't get stuck writing your commit message in Vim
 - Type git config --global core.editor "code --wait" into the VS terminal
  - What this does is you can now type git commit and after you press enter, a new tab in VS Code will open for you to write your commit messages to provide more detail on multiple lines are part of your commit message. After you type your commit message, save with Ctrl + S and close the tab
  - If you return to the command line, you will see your commit messages and a summary of your changes