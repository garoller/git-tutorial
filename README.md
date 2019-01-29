## git-workshop

Thank you to [Daniele Procida](https://dont-be-afraid-to-commit.readthedocs.io/en/latest/git/commandlinegit.html) and [Nicola Paolucci](https://www.atlassian.com/git/articles/git-forks-and-upstreams) for their amazing Git resources!

TODO: Add overview/purpose of this workshop

TODO: Add some Git conceptual stuff here (mainly just local vs. remote)... or somewhere else?

![Git conceptual](https://github.com/garoller/git-workshop/raw/master/images/git-conceptual.png)

Photo credit: [Jeff Jensen](https://www.intertech.com/Blog/introduction-to-git-concepts/)

TODO: Add description on branching vs. forking

### With Branching:

#### 1. Cloning

To start, you'll need to **clone** this **remote** repository, which creates a **local** repository.

`git clone` creates a new directory at your current location. For example, if I type:

TODO: Clean up this language/flow
```
$ pwd
/home/grace
```

```
$ git clone <repository-url>
```

Then, switch directories into your local repository:
```
$ cd <repository-name>
$ pwd
/home/grace/<repository-name>
```

#### 2. Branching


#### 3. Adding/committing

#### 4. Pushing

#### 5. Updating your branch

#### 6. Merging

#### 7. Making a Pull Request


### With Forking:

#### 1. Forking

Fork = copy (basically)

Go to the repository you want to fork: https://github.com/garoller/git-workshop

Click the Fork button. This creates your own copy of the repository.

Now go to https://github.com/your-username/git-workshop to find the fork.

#### 2. See Cloning above.

#### 3. See Adding/committing above.

#### 4. See Pushing above.

#### 5. Updating your fork
TODO: Add more description for why this is important
Check your current remotes:
```
$ git remote -v
origin	https://github.com/your-username/git-workshop.git (fetch)
origin	https://github.com/your-username/git-workshop.git (push)
```

Set upstream repository to the original repository:
```
$ git remote add upstream git@github.com:garoller/git-tutorial.git
$ git remote -v
origin	https://github.com/garoller/git-workshop.git (fetch)
origin	https://github.com/garoller/git-workshop.git (push)
upstream	git@github.com:your-username/git-tutorial.git (fetch)
upstream	git@github.com:your-username/git-tutorial.git (push)
```

Now, you can get updates from the upstream repository:
```
$ git fetch upstream
$ git merge upstream/master
```

#### 6. Merging

#### 7. Making a Pull Request






