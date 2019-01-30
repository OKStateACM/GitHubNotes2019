# Github
## Getting Started
* Create an account on [Github](github.com)
* Install Git:
  * __Windows__: Install Git from [here](https://www.git-scm.com/download). This should also install Git Bash.
  * __Linux__: Install the ``` git ``` package using whatever package manager of your choice.
  * __Mac__: Git should already be installed!
* What is Git?
Git is used for version control. This means that it maintains a record of all the changes you've made to a file or directory.
### Version control excercise
> "The quick brown fox jumped over the lazy dog"
1. Write the above sentence on a piece of paper.
2. Rewrite the above sentence, but make one change by adding, removing, or replacing a word in it.
3. Get with a couple of other people who have done these two steps. Now merge your changes into one sentence.
4. Everyone in the group copy this new sentence and make another change.
5. Merge everyone's changes together again.
### What does it mean?
What problems happened? Did multiple people change the same word? Did someone remove a word that someone else had replaced? What did you do to resolve these conflicts?

This is how the Git workflow goes.

![workflow](https://github.com/OKStateACM/GitHubNotes2019/blob/master/versionControl.png)

The above diagram shows this excercise with two people. The black line is the _master branch_ which is the default branch and should be used as the current best copy. So if you were working on a project that would be used by other people (ex. a website) then the master branch will be the working copy that other people will see. Each change to the sentence is represented by a circle. The first circle on the master branch is the original sentence.

Each person then wrote down the sentence on a piece of paper. These represent _branches_. A branch is a seperate instance of the code where a programmer will make their changes. In this case we have 2 branches, Ben and Alex. Each person's branch will have the changes that they have made without changing anything on the master branch. Then Alex's changes get merged into Ben's branch and the combined changes are merged into the master branch once both people are happy with the changes.

### Repositories

Git organizes things with _repositories_, also known as _repos_. You can think of a repository like a folder that has Git capabilites so that it can track the changes that are made.

There are _local repositories_ and _remote repositories_. Local ones are only on your machine. Remote ones are on the GitHub website, these are used for working with other people and sharing your code with other people.

There are two ways to make a remote repository. You can either create a fresh one on GitHub that doesn't have any preexisting repositories to upload, or you can create one and add repositories that already exist.

We're going to create a fresh one.
* Log in to your GitHub account and click the green "New repository" button on the right.
* Name it ``` ExampleRepo ``` and since we aren't uploading any preexisting material, click the checkbox intitialize this GitHub repo with a README. Click the "Create repository" button.
* Now you'll need to get a local version of this repository that you can make changes to, so you'll need to _clone_ it. Navigate into your repository on GitHub and click the green "Clone or download" button. Copy the link that starts with ``` git@github.com: ```.
* In your terminal, navigate to the folder where you want to keep your local version of the repo and use the ``` git clone "[Insert link you copied here]" ``` 

If you wanted to put a preexisting repo onto Github use the following steps
* Log in to your GitHub account and click the green "New repository" button on the right.
* Name it and leave the checkbox to initialize this GitHub repository with a README unchecked.
* On the next page copy the link that starts with ``` git@github.com: ```
* In your terminal, navigate into your repo and use the command ``` git remote add origin "[Insert link you copied here]". Now your local and remote repositories are connected.
* All of your files should be ready to _push_ to the local repository. So use the command ``` git push origin master ```. This will send all the commits youv'e made locally to your remote repository.
### Workflow

![commit flow](https://github.com/OKStateACM/GitHubNotes2019/blob/master/git-local-remote.png)

* Once Git has finished installing, open up the terminal that you'll be using. For Mac and Linux users, this will be your regular terminal and for Windows users it will Git Bash.
	* First you have to tell Git who you are. So if this is your first time using Git, you'll need to enter the following commands first.
		* Give Git your name using the command ``` git config --global user.name "Your name here" ```.
		* Give Git your email using the command ``` git config --global user.email "your.email@here.com" ```
* Next you'll want to create a local repository.
	* Enter the command ``` git init YourFolderNameHere ```. This will create a folder named YourFolderNameHere and make it into a repository.
	* If you already have a folder that you want to make into a repository, navigate into that folder using the ``` cd ``` command. Once inside, enter the command ``` git init ```.
* Now let's add things to our repository!
	* Create a text file, it doesn't need to have anything in it right now. Call it ``` file.txt ```.
	* We can check the status of our Git repository using the command ``` git status ```. This will let you know where you are in the git workflow.
		* When we use ``` git status ``` right now, we should get something like this:
		
		```
		On branch master
		Untracked files:
		(use "git add <file>..." to include in what will be committed)

			file.txt

		nothing added to commit but untracked files present (use "git add" to track)
		```
	* Git doesn't save every change you make to your code. It stores snapshots called _commits_ you can think of these like saving your file. When you save it, it takes a new snapshot of your file that includes all the changes you've made since the last save. It's the same way with commits. 
	* Now that we have a file, we need to add it to the staging area, which is the first stage in a commit, it allows you to still make changes without it being documented in a commit message. To do this, enter the command ``` git add file.txt ```, or if you want to add all files in a repo use the command ``` git add . ```.
	* If we call ``` git status ``` now, you should get something like this
	
	```
	On branch master
	Changes to be committed:
	(use "git reset HEAD <file>..." to unstage)

		new file:   file.txt
	```
	* This is saying that all the changes we've made since the last snapshot will be in the next commit.
	* Once we have added all the files we want to the staging area, we're ready to commit to our local repository. To do this, use the command ``` git commit -m "Enter a commit message here!" ```. Every commit should have a _commit message_ which should be useful description of all the changes you've made since the last commit.
	* After committing, use the ``` git status command ```. It should look like this
	```
	On branch master
	nothing to commit, working tree clean
	```
	* Doing the add and commit stages seperatly can be annoying, so if you want to combine these steps, you can use ``` git commit -am "Your commit message here!" ```.
	* You want to commit often, good practice is to commit every time you've added a working feature.
	* Once you want to add all the commits you've been working on to the remote repo on the GitHub website, you'll need to _push_ them. This will push all the things in your local repo to your remote one. You can do this by using ``` git push ```
### Branching
* Good practice is to not commit directly to the master branch, especially at enterprise level. So, to make changes you'll need to make a _branch_, it's essentially a copy of another branch - typically the master branch - that you can work on without editing the master branch.
* We're going to create a branch from our master branch called ``` branchname ```, after making sure you're in your repo, use the command ``` git branch branchname ```.
* Your ``` git status ``` should now say 
```
On branch master
nothing to commit, working tree clean
```
* As you can see, we're still on our master branch. To change to our newly created branch, use the command ``` git checkout branchname ```.
* All the changes you commit will now go to your new branch instead of to the master branch. If you want to check and make sure, use ``` git checkout master ``` and open your file. None of the commits you've added to your other branch should be there.
* When you're satisfied with all the changes you've made in your branch and are ready to merge it with master, make sure you are on your branch and use the command ``` git merge master ```.
* If there have been changes added to master that conflict with your changes, then there will be a _merge conflict_, and Git Bash won't let you merge your branch into master until you've gone through and resolved these conflicts, which means you'll have to go through the conflicts and decide which should stay.
* You can set your repo to require a _pull request_ which means that people can request to merge their branch with master. This is often used to ensure code review happens.
### Pulling
If changes are made within the remote repository, our local repository won't be automatically updated. In order to get the changes, we'll need to pull them to our local repo. To do so, use the ``` git pull ``` command. 