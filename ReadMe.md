### Introduction to Git and Github

:::author
Allan Wasega
:::

#### Introduction


#### What is Git?

#### What is Github?

#### Create a Repository on Github

![](create_repository.png)

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

```
