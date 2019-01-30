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

### Repositoris

Git organizes things with _repositories_, also known as _repos_. You can think of a repository like a folder that has Git capabilites so that it can track the changes that are made.

## Workflow

* Once Git has finished installing, open up the terminal that you'll be using. For Mac and Linux users, this will be your regular terminal and for Windows users it will Git Bash.
	* First you have to tell Git who you are. So if this is your first time using Git, you'll need to enter the following commands first.
		* Give Git your name using the command ``` git config --global user.name "Your name here" ```.
		* Give Git your email using the command ``` git config --global user.email "your.email@here.com" ```
* Next you'll want to create a repository.
	* Enter the command ``` git init YourFolderNameHere ```. This will create a folder named YourFolderNameHere and make it into a repository.
	* If you already have a folder that you want to make into a repository, navigate into that folder using the ``` cd ``` command. Once inside, enter the command ``` git init ```.