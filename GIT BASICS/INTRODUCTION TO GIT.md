INTRODUCTION
 - Git is a version control system that saves for my files and directories
 - A save in a text editor records all the words in a document as a single file
 - A save in GIt record differences in the files and folders AND keeps a historical record of each save
    - You are able to review how your project grows and to easily look at or restore file states from the past
    - When connected to a network, Git allows you to push you project to GitHub for collaboration
 - Git works on your local machine, whereas GitHub is a remote storage facility on the web

LESSON OVERVIEW
 * Explain what Git and GitHub are and the differences between the two
 * Describe the differences between Git and a texteditor in terms of what they save and their record keeping
 * Describe why Git is useful for an individual developer and a team of developers


About Version Control
 - A version control is a system that records changes to a file over time so that you can recall specific versions later
 
 Local Version Control Systems
  - A well-knows version-control method is to copy files into another directory but it is error prone
    - To deal with this issue, programmers developed local VCSs that had a simple database that kept all the changes to files under revision control
  - RCS (an early implementation of VCS) works by keeping patch sets that is able to re-create what any file looked at any point

 Centralized Version Control Systems
  - To be able to collaborate with other developers on other systems, the Centralized Version Control Systems (CVCS) was created
  - These systems hae a single server that contains all the versioned files, and a number of clients that check out files from that central place
  - It allows everyone to know what everyone else on the project is doing to a certain degree and admins have fine-grained control over who can do what, and it is easier to administer a CVCS
  - If the server goes down, however, no one could collaborate at all or save versionedchanges to anything they're working on
  - If the hard disk for the central database becomes corrupted and there are no backups, you lose everything
 
 Distribued Version Control Systems
  - In Distributed Version Control Systems (DVCSs), clients don't just check out the latest snapshot of the files; rather they fully mirror the repository
    - Thus, if any server dies, and these systems were collaborating via that server, any of the client repositories can be copied back up to the server to restore it


Getting Started - What is Git?
 
 Snapshots, Not Differences
  - The major difference between Git and any other VCS is the way Git thinks about its data
  - Most other systems store information as a set of files and the changes made to their file over time (delta-based version control)
  - Git instead thinks of data more like a series of snapshots of a mini filesystem
    - Every time you commit (save) a project, Git takes a picture of what all your files look like at that moment and stores a reference to that snapshot
    - Git doesn't store the file again, just a link to the previous identical file it has store (stream of snapshots)
 
 Nearly Every Operation is Local
  - Most operations in Git need only the local files and resources to operate
    - Because you have the entire history of the project is on your local disk, most operations seems instantaneous
  - For example, to get the history of the project, Git does not need to go out to the server to get the history and display it for you because it simply reads it directly from your local database
    - You are able to work offline because the data will be stored into your local drive until you are connected to the internet or VPN where you can commit your changes there

 Git Has Integrity
  - Everything in Git is checksummed before it is stored (impossible to change contents of the file or directory without Git knowing about it) so you can not lose information in transit or get file corruption without Git being able to detect it
    - Git uses SHA-1 has for checksumming

 Git Generally Only Adds Data
  - When doing actions in Git, they nearly all add data to the database so it is hard to get the system to do anything that is not unddoable to to erase data

 The Three States
  - Three main states: modified, stages, and commited
   1. Modified: Changed the file but not yet commited to your database yet
   2. Staged: Marked a modified file in its current version to go into your next commit snapshot
   3. Commited: Data is safely stored in your local database
  - There are three main sections of a Git project tree: the working tree, the staging are, and the Git directory
   1. Working tree: A single checkout of one version of the project. These files are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify
   2. Staging area: A file generally contained in your Git directory that stores information about what will go into the next commit (also called the index)
   3. Git directory: Where Git stores the metadata and object database of a project. Most important part of Git, and it is what is copied when you clone a repository from another computer
  - Basic Git workflow:
   1. You modify files in your working tree
   2. You selectively stage just those changes you want to be part of your next commit, which adds only those changes to the staging area
   3. You do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory
 - If a particular version of a file is in the Git directory, it is considered committed. If it has been modified and was added to the staging are, it is staged. And if it was changed since it was checked out but has not been staged, it is modified

The Command Line
 - You can use Git using the original command-line tools, and there are many graphical user interfaces of varying capabilites
 - The command line is the only place you can run all Git commands and all users will have the command-line tools installed and available