# TransUnion workshop

## Contents

 1. Intro to GIT
 3. Create first commit
 4. Create GitHub repository
 5. Push/Save and Pull/Download changes from GitHub
 6. Create first branch and work with it
 7. Merge branches
 8. Merge conflicts


## Intro to GIT

What wiki says: 
**Git** is a ****distributed** version-control** system for tracking changes in source code during software development. It is designed for coordinating work among programmers, but it can be used to track changes in any set of files. Its goals include speed, data integrity, and support for distributed, **non-linear workflows**.

**Version-control** - How we do version control:

![enter image description here](https://i.ibb.co/4PMH3YV/Screenshot-2.png)

How git version control looks like:

![enter image description here](https://user-images.githubusercontent.com/18033666/40845217-0a1ec660-6584-11e8-8e74-37a68fae953b.png)

**Distributed version-control** - all files and history are saved in every programmers computer, also it can be saved in central file. Every body, has copy of all files and history and all clients can work offline and **merge** all changes at end of day/week.

**Linear workflow** - when everybody is working on same version of project, same version of file etc.

**Non-linear workflow** - when everybody has it's own version of file.

![enter image description here](https://i.ibb.co/Ky9Mcxt/Untitled-Diagram.png)


## Create first local repository (individual work starts here)
First let's create new project directory and open git bash in project directory

![enter image description here](https://i.ibb.co/NWkZFgV/Screenshot-1.png)

We should see git bash terminal:

![enter image description here](https://i.ibb.co/qDXGyDr/Screenshot-3.png)

Then we can also configure our git client:

     git config --global user.email "mariukaz@gmail.com"
     git config --global user.name "MariusM"


![enter image description here](https://i.ibb.co/wyZG6Pw/Screenshot-7.png)

Now lets create git repository with command:

    git init
We should see:

![enter image description here](https://i.ibb.co/RyT44Kh/Screenshot-4.png)

And that's it we created local repository:)


## Create first commit
First let's add demo.php file to that repository which contains:

    <?php
    print "Hello php and git!"
    
    
![enter image description here](https://i.ibb.co/tDsmKyb/Screenshot-5.png)

To commit something to local GIT repository we have to add that file to staging area with command:

    git add demo.php
    
![enter image description here](https://i.ibb.co/bg9TcH1/Screenshot-6.png)

> You can use `git add *` if you want to stage all files

Now we can commit all staging files to local repository:

    git commit -m "My first commit to git"
   ![enter image description here](https://i.ibb.co/xLqjkTZ/Screenshot-8.png)
   

## Create GitHub repository
Register to https://github.com/

After logging in to your GitHub dashboard press "New"

![enter image description here](https://i.ibb.co/cQP992v/Screenshot-9.png)

Enter repository name and create it:

![enter image description here](https://i.ibb.co/k6Sr66v/Screenshot-11.png)

Great, now we have our remote GitHub repository:

![enter image description here](https://i.ibb.co/xCLzVzC/Screenshot-12.png)


## Push/Save and Pull/Download changes from GitHub

First let see what GitHub tells us:

![enter image description here](https://i.ibb.co/ySNF6H9/Screenshot-14.png)

From this page we see that my git repository is at address: 

    https://github.com/Markomas/tutapro.git
And if we want to push an existing repository (which we created while doing "Create local repository"), we need to run these commands:

    git remote add origin {your repository}
    git push -u origin master

> Change {your repository} to your repository URL
 
> `git push -u origin master` origin - default remote repository in our case it's https://github.com/Markomas/tutapro.git. master is branch to which we are pushing changes. If remote branch doesn't exits it will be created automagically

While running "git push -u origin master" we should get GitHub login page:

![enter image description here](https://i.ibb.co/PW9fXmN/Screenshot-15.png)

And after successful login and push we should get:

![enter image description here](https://i.ibb.co/kxrq1rM/Screenshot-16.png)

Now let's reload our GitHub repository:

![enter image description here](https://i.ibb.co/cXgMcvv/Screenshot-17.png)

Cool now we see that our local repository has been synced with GitHub repository. This means that our local changes has been saved to cloud.
Because git is **Distributed version-control** this means that our files and history is saved in our local computer and GitHub servers. If our cat spills coffee on our laptop, no worries we can get these files from GitHub. And if GitHub cat spills coffee on GitHub servers no worries we have all files and history on our local computer and we can push this files again.

Now let's add new file to GitHub and pull/download these files to our local computer.

![enter image description here](https://i.ibb.co/YZ8y0rW/Screenshot-19.png)

And then fill fields like this:

![enter image description here](https://i.ibb.co/wpQNy8y/Screenshot-18.png)

And now we can see that file in GitHub repository:

![enter image description here](https://i.ibb.co/2PThv4b/Screenshot-21.png)

But wait we don't see that file in our local computer, we have different versions of same project local computer. How we could solve this?
Well it's easy we need just to download that remote repository to our local computer with these commands:

    git fetch
    git pull
   The we should see
   
![enter image description here](https://i.ibb.co/0rPCRVm/Screenshot-22.png)

> `ls` - is terminal command which list all files in current directory
> `git fetch` - updates remote branch list (we will talk about branches in section "Create first branch and work with it")
> `git pull` - downloads remote changes to current branch

## Create first branch and work with it
Well what is branch?

![enter image description here](https://i.ibb.co/F7m43PC/Untitled.png)

Branches are used to develop features isolated from each other. The _master_ branch is the "default" branch when you create a repository. Use other branches for development and merge them back to the master branch upon completion.

So all this time we were working on master branch, but usually we don't work on this branch directly.
Let's check current branch:

    git branch


![enter image description here](https://i.ibb.co/fDMQZKV/Screenshot-23.png)

so let's create local branch and checkout it:

    git checkout -b feature_x
![enter image description here](https://i.ibb.co/YjYGp9m/Screenshot-24.png)

As we see we were on `master` then we created `feature_x`branch and checked out that branch.

> Branch marked green with star is current branch

> Created branch is identical to branch from witch we created it in this case it has same files as `master`

How to get back to `master` branch?

    git checkout master
![enter image description here](https://i.ibb.co/3fw1KQf/Screenshot-25.png)

And how to delete branch?

    git branch -d feature_x
![enter image description here](https://i.ibb.co/RTnRPYp/Screenshot-27.png)

Great we know how to create, delete and switch branches in our local repository.

Now small task for you:

 1. Create new branch named as `feature/adding-third-file` and switch to it
 2. Create new file in your local computer which is named as `third.php` with random content
 4. Stage that file and commit it to your local repository
 5. Push branch `feature/adding-third-file` to GitHub.

After all steps we should see in our git hub repository that we have new branch named as `feature/adding-third-file`:

![enter image description here](https://i.ibb.co/Wv5Q0CV/Screenshot-28.png)

And entering it we will see our new file is created in that branch: 

![enter image description here](https://i.ibb.co/X8CN73T/Screenshot-29.png)

> In normal work case, one developer would be working on one branch and doing these changes, other developer would be using other branch and so on.

> If you had issues with that task it's little help for you:)
> git checkout -b feature/adding-third-file
> Create file third.php
> git add .
> git commit -m "Adding third file"
> git push origin feature/adding-third-file
## Merge branches

Now we know how to create branches, but how do we merge these branches to `master`? 
We could use command: `git merge {branch}` it merges branch  named as {branch} to current active branch.
So if we want to merge: `feature/adding-third-file` to `master` we have to:

    git checkout master
    git merge feature/adding-third-file
    
and if want to push these changes to GitHub, we can push `master`

![enter image description here](https://i.ibb.co/6XsmLmm/Screenshot-30.png)

And to confirm that we can open our GitHub page and we will see in our `master` branch that we have `third.php`.

![enter image description here](https://i.ibb.co/W2y3jT2/Screenshot-31.png)

## Merge conflicts
Small task for you:

 1. Create new branch named as `feature/adding-fourth-file` and switch to it
 2. Create new file in your local computer which is named as `fourth.php` with text:

	    <?php
   
	    print "hello world mate";
	    print "it's fourth file made today";
	    print "by git";

 3. Stage that file and commit it to your local repository
 4. Push branch `feature/adding-fourth-file` to GitHub.
 5. Then checkout master or main branch
 6. Then create another branch `feature/adding-another-fourth-file` and switch to it
 7. Create new file in your local computer which is named as `fourth.php` with text :

    	<?php

	    print "hello world mate";
	    print "it's fourth file made by me today";
	    print "by git";
8. Stage that file and commit it to your local repository
9. Push branch `feature/adding-another-fourth-file` to GitHub.

Great now we have 2 new branches and each of them contains new file: `fourth.php` but wait, these files are different? What would happen if we try to merge both these files to `master` ?

Let's try it out:

     git checkout master
     git merge feature/adding-fourth-file
     git merge feature/adding-another-fourth-file

![enter image description here](https://i.ibb.co/Jsm3rRr/Screenshot-32.png)

Oh with second merge we got message:

	CONFLICT (add/add): Merge conflict in fourth.php
	Auto-merging fourth.php
	Automatic merge failed; fix conflicts and then commit the result.

This means that git was unable to decide which things from one or another file should be kept in master branch. To help git to choose right things we need to solve it by ourself.

If we open file `fourth.php` now we would see: 

![enter image description here](https://i.ibb.co/YchhfM8/Screenshot-33.png)

If file is big to see the beginning of the merge conflict in your file, search the file for the conflict marker `<<<<<<<`. When you open the file in your text editor, you'll see the changes from the HEAD (current branch in this case it's master) or base branch after the line `<<<<<<< HEAD`. Next, you'll see `=======`, which divides your changes from the changes in the other branch, followed by `>>>>>>> BRANCH-NAME`. 
If we now we have to decide what choose:

    print "it's fourth file made by me today";
    or
    print "it's fourth file made today";
    or keep both, or do other changes
  Let's pick line `print "it's fourth file made by me today";` we have to remove
File should look like: 

    <?php
    
    print "hello world mate";
    print "it's fourth file made by me today";
    print "by git";
Now let's stage files with `git add .` and commit it 

    git commit -m "Resolved my first merge conflict"
    git push origin master
