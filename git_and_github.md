# Git basic workflow

## Github setup

1. Create a new repository.
2. Give a name and check "Add a README file". Then, click on create repository.
3. Copy SSH URL.
4. Now clone the repository, with:
`git clone [SSH url].`

## Git Workflow

1. `git add [file]`
2. `git commit -m "Message"`
3. `git push`

`git status` To see the status of the files.

`git log` To see the log.

## Messages

1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line
7. Wrap the body at 72 characters
8. Use the body to explain what and why vs. how

#### What is git? 
It's like a save button for your files and directories. Oficially, it's a
version control system. A version control system specifically designed to 
work well with text files. Git is a program you install which allows you to 
annotate the changes you make to create an easily navigable system history. A save here 
records the differences in the files and keeps a historical record of each save. 

This lets you to review how your project grows and to easily look at or restore
file states from the past. Once connected to a network, it allows you to push
your project to Github, or other alternatives.

#### What is github?
Unlike Git which works on your local machine, GitHub is a remote storage facility
on the web for coding projects. Github takes that lovely commit history and hosts 
it online so that you can access it from any computer. 

You do this via pushing commits from your local machine up to Github, and then, 
from the new/different computer pulling those commits down.

#### Local, centralized, and distributed version control systems
First of all, version control is a system that records changes to a file or
set of files over the time, so that you can recall specific versions later.

###### Local Version Control Systems
Many people’s version-control method of choice is to copy files into another 
directory. To deal with this issue, programmers long ago developed local VCSs 
that had a simple database that kept all the changes to files under revision 
control.

One of the most popular VCS tools was a system called RCS, which is still 
distributed with many computers today. RCS works by keeping patch sets 
(that is, the differences between files) in a special format on disk; 
it can then re-create what any file looked like at any point in time by 
adding up all the patches.

###### Centralized Version Control Systems
To deal with the problem of needing to collaborate with other developers,
this was created. These systems have a single server that contains all the
versioned files, and a number of clients that check out files from that 
central place. 

This offers many advantages over VCSs. Everyone knows to a certain defree what
everyone else is doing. Administrators have fine-grained control over who can
do what, and it's far easier to administer this than it's to deal with local
databases on every client.

This has some serious downsides. If the server goes down, nobody can collaborate
or save versioned changes. If it becomes corrupted, and there's no backup, you
lose everything. Local VCSs suffer from this problem.

##### Distributed Version Control Systems
Here, clients fully mirror the repository, including its full history. If any 
server dies, and these systems were collaborating via that server, any of the 
client repositories can be copied back up to the server to restore it. Every 
clone is really a full backup of all the data.

This allows you to set up several types of workflows that aren’t possible in 
centralized systems, such as hierarchical models.


