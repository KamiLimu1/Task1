### Introduction to Git and Github

:::author
Allan Wasega
:::

#### Introduction


#### What is Git?

#### What is Github?

#### Create a Repository on Github

![](create_repository.png)

```important
Select ```Create a readme file``` while creating your repository. This is a form of documentation that contains information about the other files in your repository or even what the repository aims to achieve. 
In my case, I have left it unselected as I will be creating a ReadMe locally.
```  

### Setting up Git


```json
git init 
```
This will initialize (start) git inside the folder (repository) in which you are working. 
The result will look something like this: 

![](git_init.png)

Most other Git commands are not available outside of an initialized repository, so this is usually the first command you'll run in a new project.

:::note
The ```git init``` command creates a new Git repository. It can also be used to convert an existing unversioned project to a Git repository (which is what we have done above) or initialize a new, empty repository. 


### Clone the repositiory you created on Github

:::note
```Clone``` means to create copy the repository in Github (the remote repository) so that you can work on it from your local machine. 

The ##clone## operation is done using the ```git clone``` command line utility in Git. 
:::

1. To create a clone of your remote repository (the one on Github), head over to the repository and copy the link given under ```Quick setup``` as shown below:

![](clone1.png)

2. Head over to your terminal and enter
```json
git clone + (copied link)
```
![](clone2.png)

Ignore the warning because we did not create any file within the remote repository while creating it.

### Create a file locally and store it remotely

1. Using your favorite code editor (I am using SublimeText, for example), create a file and, in it, write a piece of code in a programming language of your choice. 

2. Use Git to ```push``` this file from your local to remote repository

```Pushing``` is how you transfer your local files, and any changes they contain, to a remote repository. This is done using the ```git push``` command. However, reign in on your excitement because there are a few checks to be done first before we can do the ultimate push. 

a. Do a ```git status.```

This command allows you to check the state of your current working directory. Through it, you can check which changes have been staged and the files that are not being tracked by Git. 

For example, in the image below, none of my files in the folder in which I am working is being tracked by Git. Running ```git status``` also shows you what branch you are on. We will cover branches and how to navigate them later. However, note that, in this case, we are on ```master```, which is the default branch on Git. 

b. Add the file you created to the staging area using ```git add```
The staging area is like a rough draft space, where you can add and remove versions of file before transferring them to the remote repository. 

What ```git add``` command does is to copy this file (or a version of it) from your working directory to the staging area. 

:::important

```git add``` can take one of two arguments. 

- **git add .** to add all the files in your directory to the staging area, or
- ** git add <file name> to add a file by its name to the staging area. 
:::

In my case, I want to push both the ReadMe.md and SimplePython.py files. When I run ```git status``` again, the two files have been added to the staging area and the rest are untouched.  

![](git_add.png)

:::note
At this point, you can remove a file from the staging area using the ```git rm --cached <file>``` command. 

Try it out to unstage the file you added then stage it again to proceed. 
:::

c. From here, we can now push the files to our remote repository. 
Typically, this is a two-stage process that proceeds as follows: 

- First, we ```commit``` the changes using the command ```git commit -m "message" ```
A **commit** is simply your way of capturing a snapshot of the current changes that you have made to your local repository. Once you perform a commit, Git will never change the captured snapshot unless you ask it to. Note that commits are done locally and, at this stage, no changes have been made to the remote repository yet. 

For example, below, I will commit the two files with the message *First commit*

![](git_commit.png)

The ```-m``` flag tells git to create the commit with the given message. Other options are available: 
- ```git commit```: Commit the staged snapshot. This will launch a text editor prompting you for a commit message. After you’ve entered a message, save the file and close the editor to create the actual commit.
- ```git commit -a```: Commit a snapshot of all changes in the working directory. This only includes modifications to tracked files (those that have been added with git add at some point in their history)
- ```git commit am "commit message"```: A power user shortcut command that combines the -a and -m options. This combination immediately creates a commit of all the staged changes and takes an inline commit message.

:::note
A **git commit** to the local directory can be reversed. This can be achieved using the ```git revert``` command, which takes various arguments. In this case, we will use the SHA checksum of the commit we want to reverse. To get the SHA checksum, do a ```git log``` command as shown below. Then proceed to perform a ```git revert <SHA>```.
	




