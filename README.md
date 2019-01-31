## git-workshop

Thank you to [Daniele Procida](https://dont-be-afraid-to-commit.readthedocs.io/en/latest/git/commandlinegit.html) and [Nicola Paolucci](https://www.atlassian.com/git/articles/git-forks-and-upstreams) for their amazing Git resources!

TODO: Add overview/purpose of this workshop

TODO: Add some Git conceptual stuff here (mainly just local vs. remote)... or somewhere else?

![Git conceptual](https://github.com/garoller/git-workshop/raw/master/images/git-conceptual.png)

Photo credit: [Jeff Jensen](https://www.intertech.com/Blog/introduction-to-git-concepts/)

### What you need to have installed:
1. A text editor of your choice (my favorite is [VS Code](https://code.visualstudio.com/docs/setup/setup-overview))
2. Git on the command line
    * TODO: find clear WSL installation instuctions
    * Installation instructions for Linux and macOS [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

TODO: Add description on branching vs. forking

### With forking:

#### 1. Create your own remote repository

Go to the repository you want to fork, for this tutorial it's: https://github.com/garoller/git-workshop, and click the Fork button. This creates your own copy of the repository.
Now go to https://github.com/your-username/git-workshop to find your forked repository.


#### 2. Create a local repository

To start, you'll need to **clone** the **remote** repository, which creates a **local** repository.
```
git clone https://github.com/your-username/git-tutorial.git
```
this creates a new directory at your current location. For example, if I type:

TODO: Clean up this language/flow
```
>> pwd
/home/grace
>> git clone https://github.com/your-username/git-tutorial.git
```

Then, switch directories into your local repository:
```
>> cd git-tutorial
>> pwd
/home/grace/<repository-name>
```

#### 3. Make and save changes

```
git add <path/file_with_changes>
git commit -m "Descriptive commit message"
```

#### 4. Update your remote repo

```
git push origin master
```

#### 5. Update your fork with upstream changes

TODO: Add more description for why this is important, define `upstream`

Check your current remotes:
```
>> git remote -v
origin	https://github.com/your-username/git-workshop.git (fetch)
origin	https://github.com/your-username/git-workshop.git (push)
```

Set upstream repository to the original repository:
```
>> git remote add upstream git@github.com:garoller/git-tutorial.git
>> git remote -v
origin	https://github.com/garoller/git-workshop.git (fetch)
origin	https://github.com/garoller/git-workshop.git (push)
upstream	git@github.com:your-username/git-tutorial.git (fetch)
upstream	git@github.com:your-username/git-tutorial.git (push)
```

Now, you can get updates from the upstream repository:
```
>> git fetch upstream
>> git merge upstream/master
```

#### 6. Resolving conflicts

#### 7. Making a pull request


### Branching:

#### 1. Create a local branch

#### 2. See make and save changes above

#### 3. See update your remote repo above

#### 5. Update your branch with changes on remote master branch

#### 6. Resolving conflicts

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

TODO: Decide if we want to keep the SSH stuff

Clone using SSH:
```
git clone git@github.com:your-username/git-tutorial.git
```

[Generating an SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

[Add SSH key to Github account](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)




TODO: Slides - what git is, explain what the commands are doing, talk about why git -> version control is necessary
