## git-workshop

Contributors: <your-name-here>

Thank you to [Daniele Procida](https://dont-be-afraid-to-commit.readthedocs.io/en/latest/git/commandlinegit.html) and [Nicola Paolucci](https://www.atlassian.com/git/articles/git-forks-and-upstreams) for their amazing Git resources!

TODO: Add overview/purpose of this workshop

TODO: Add some Git conceptual stuff here (mainly just local vs. remote)... or somewhere else?

![Git conceptual](https://github.com/garoller/git-workshop/raw/master/images/git-conceptual.png)

Photo credit: [Jeff Jensen](https://www.intertech.com/Blog/introduction-to-git-concepts/)

### What you need to have installed:
1. A text editor of your choice (my favorite is [VS Code](https://code.visualstudio.com/docs/setup/setup-overview))
2. Git on the command line
    * Windows options:
        - Use WSL (Windows Subsystem for Linux) and follow Linux instructions below for Ubuntu
        - [Git download](https://git-scm.com/downloads). During installation select Git bash (UNIX emulator) or the Windows Command Prompt
    * [Linux and macOS](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### Setup Git

Tell Git who you are, so it can associate changes with your Github account:
```
>> git config --global user.name "your-username"
>> git config --global user.email "your-email"
```
Check that it worked:
```
>> git config --list
user.name=your-username
user.email=your-email
```

### Branching vs. forking
Creating a branch copies the code from one brach and allows you to 
Forking a repository creates a separate copy of the repository, including it's all of it's branches, under your account. 

### With forking:

#### 1. Create your own remote repository

Go to the repository you want to fork, for this tutorial it's: https://github.com/garoller/git-workshop, and click the Fork button. This creates your own copy of the repository.
Now go to https://github.com/your-username/git-workshop to find your forked repository.


#### 2. Create a local repository

You'll **clone** the **remote** repository, which creates a **local** repository.

```
>> git clone https://github.com/your-username/git-tutorial.git
```

this creates a new directory at the current location. For example, if I type:

```
>> pwd
/home/grace
```

to see my current path. Then, clone the repository:

```
>> git clone https://github.com/your-username/git-tutorial.git
```

switch directories into the repository:

```
>> cd git-tutorial
>> pwd
/home/grace/git-tutorial
```

#### 3. Make and save changes

Open the folder in with the text editor of your choice.

If you're using VS Code, type:

```
>> code .
```

to open the current folder.

Then, add your name to `Contributors` list in this file.

After that you're ready to **stage** your changes.

```
>> git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

`git status` gives you a breakdown of the current state of the branch you're on.

Git knows you've made changes, but you have to stage them before you can save them.

To stage your changes:

```
>> git add README.md
```

Type `git status` again to see the difference.

Now that you're changes are staged, you can save them to Git, by making a **commit**.

```
>> git commit -m "Add name to contributor list"
```

The `-m` flag stands for message, which allows you to enter the commit message inline, rather than opening a text editor in the terminal, which can be confusing to navigate.

Now, type `git status` again and notice the difference.

To see your commit, enter `git log`.

#### 4. Update your remote repo

Now that you've made your first commit on the **local** repository, you want those changes to be reflected on the **remote** repository. To do that, enter:
```
>> git push origin master
```

Take a look at the `README.md` on your account's git-workshop repo to see your changes!

#### 5. Update your fork with upstream changes

# Should we switch the order of 4 & 5?


At this point, after you've made changes and pushe them to the remote, the next steps are getting ready to integrate your changes into the original repository. 
The repository where you forked from is known as the **upstream** repository, and the forked repository is the **downstream**.
In this tutorial, upstream = garoller/git-workshop and downstream = your-username/git-workshop.

Since you cloned the repository from your account, **origin** is your-username/git-workshop.

To verify this, check your current remotes:
```
>> git remote -v
origin	https://github.com/your-username/git-workshop.git (fetch)
origin	https://github.com/your-username/git-workshop.git (push)
```

Now, you can add the upstream repository to your remotes:
```
>> git remote add upstream git@github.com:garoller/git-tutorial.git
>> git remote -v
origin	https://github.com/your-username/git-workshop.git (fetch)
origin	https://github.com/your-username/git-workshop.git (push)
upstream	git@github.com:garoller/git-tutorial.git (fetch)
upstream	git@github.com:garoller/git-tutorial.git (push)
```

You can update from the upstream repository:
```
>> git fetch upstream
>> git merge upstream/master
```

#### 6. Resolving conflicts

At this step, you might have encountered a merge conflict. 

If you don't have any merge conflicts though, that's great, and you're ready for
the next step.

#### 7. Making a pull request


### Branching:

#### 1. Create a local branch

Create a new branch, 
```
>> git checkout -b new-branch-name
```
`-b` creates a new branch, and `checkout` immediately switches to that branch.

To get to switch to an existing branch, just use:
```
>> git checkout branch-name
```

#### 2. See make and save changes above

Make any change(s) you wish to the file on your `new-branch-name`, and add and commmit those changes like you did above.

#### 3. Update your remote repo

The steps are almost the same as above, except instead of pushing to remote `master`, you'll want to create a remote branch `new-branch-name`. 

By entering:
```
git push origin new-branch name
```

the remote `new-branch-name` is created if it doesnt exist already.

#### 5. Update your branch with changes on remote master branch

If the project you're working on uses branching, you don't have to worry about an upstream repository. Instead, other contributors working on the same project will update the remote master. To make sure you're working with the current code base and to resolve any conflicts locally it is good to:
```
git fetch
git merge origin/master
```

regularly.


#### 6. See resolving conflicts above

#### 7. Making a pull request

TODO: describe that branching and forking can be (and often are) done separately

### Miscellaneous

#### Git ignore
TODO: this section

#### Helpful commands

`git log` - shows the local commit history

`git status` - shows what branch you're currently on, and staged, unstaged, and untracked files

`git branch` - shows all local branches

`git stash` - removes all uncommitted changes from the working directory, but stores them to use for later

`git stash pop` - applies the latest stashed changes back onto the working directory

`git reset --hard` - deletes all uncommitted changes

`git reset .` - unstages all staged files

`git checkout <filename>` - removes all uncommitted changes from `filename`

`git reset HEAD~1` - removes the most recent commit 

#### Setting up an SSH key

Clone the repository using SSH:
```
git clone git@github.com:your-username/git-tutorial.git
```

[Generating an SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

[Add SSH key to Github account](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
