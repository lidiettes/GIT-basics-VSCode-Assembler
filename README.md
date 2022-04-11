`#git-basics` `#assembler-institute` `#master-in-software-development`

# Assembler Institute: Git basics - Console exercises <!-- omit in toc -->

<img src="https://raw.githubusercontent.com/assembler-institute/git-basics-1/main/utils/git_logo.png" width="500px"></img>

With these exercises you will learn how to use git in your console.

## Introduction

Git is a version control software designed by Linus Torvalds, thinking about the efficiency and reliability of maintaining application versions when they have a large number of source code files. Its purpose is to keep track of changes in computer files and coordinate the work that several people do on shared files.

## What are the main objectives in this project?

- Understand what version control is and what it is used for
- Understand what GIT is and its fundamentals
- Become familiar with repositories

## 1. General analysis (Read the full requirements before starting the exercises)

### 1.1 Install GIT

The first step is to install git to start using it. To do this, follow the steps indicated in the official guide:
- [Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

It is important that once installed, you configure GIT correctly, to do this follow the steps indicated in the official guide:
- [First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

### 1.2 Git Local Repository

Next, you will need to follow the instructions to complete the exercises:

**1.2.0 Clone the repository to create a local copy on your computer:**
[https://github.com/assembler-institute/git-basics-1.git](https://github.com/assembler-institute/git-basics-1.git)

**1.2.1 exercise-01: Create a new file and add it to the staging area**

1. Create a new file named: `exercise-01.txt` inside the `src/exercises folder`
2. Add any text value inside the new file and save the new file
3. Add the file to the staging index with the `git add 'file-name'` command
4. Execute the: `npm run validate-exercise-01` command from the  terminal to validate your solution to the exercise

**1.2.2 exercise-02: Create a commit with the new file**

1. Use the `git commit -m 'commit-message'` command to create a new commit based on the changes in the staging area that have the new file you just created
2. Use a commit message of: `'exercise-02 commit'`
3. Execute the: `npm run validate-exercise-02` command from the  terminal to validate your solution to the exercise

**1.2.3-a exercise-03-a: Create 2 new files and add all of them to the staging area**

1. Create 2 new files inside the `src/exercises` folder with the names of:
    1. `exercise-03-a.txt`
    2. `exercise-03-b.txt`
2. Add any text value inside each file and save them
3. Add all of them to the staging area with the `git add --all` command
4. Execute the: `npm run validate-exercise-03-a` command from the  terminal to validate your solution to the exercise

**1.2.3-b exercise-03-b: Create a new commit with the new files**

1. Create a commit with all the new files with the commit message of: `'exercise-03 commit'`
2. Execute the: `npm run validate-exercise-03-b` command from the  terminal to validate your solution to the exercise

**1.2.4-a exercise-04-a: Make a change and add it to the staging index**

1. Change the content of the `exercise-03-a.txt` file and add the changes to the staging index with the `git add` command
2. Execute the: `npm run validate-exercise-04-a` command from the  terminal to validate your solution to the exercise

**1.2.4-b exercise-04-b: Use git reset to unstage the changes**

1. Run the `git reset HEAD src/exercises/exercise-03-a.txt` command to unstage the changes from the staging index
2. Now you should see that the changes were added back to the working directory and out of the staging index
3. Execute the: `npm run validate-exercise-04-b` command from the  terminal to validate your solution to the exercise

**1.2.5 exercise-05: Use git checkout -- to discard all the changes made to a file**

1. Run the GIT command to discard the changes made to the file:
    * `git checkout HEAD -- src/exercises/exercise-03-a.txt`
2. This command will remove all the changes you made to the file and they will be deleted. This is useful if you don’t want to keep the changes that you made so far.
3. **NOTE**: This command removes the changes, you will not be able to recover them once they are removed.
4. Execute the: `npm run validate-exercise-05` command from the  terminal to validate your solution to the exercise

### 1.3 Git Branches

**1.3.1 exercise-06: Create a new branch named develop**

1. Execute the `git branch` command to see the branch you are currently in
2. Create a new branch named `develop` with the git command:
    * `git branch develop`
3. Execute the `git branch` command to see a list of the branches
4. Execute the: `npm run validate-exercise-06` command from the  terminal to validate your solution to the exercise

**1.3.2 exercise-07: Switch to the develop branch and create a new commit**

1. Execute the `git checkout 'branch-name'` command to switch to the new branch you just created:
    * `git checkout develop`
2. Create a new file named `exercise-07.txt` in the  the `src/exercises` folder that has any value inside and create a new commit with the new file
3. Execute the: `npm run validate-exercise-07` command from the  terminal to validate your solution to the exercise

**1.3.3 exercise-08: Create a new branch named `feature` based on the `develop` branch**

1. Create a new branch named `feature` based on the branch `develop`
2. Switch to the `master` branch using `checkout`
3. Execute the: `npm run validate-exercise-08` command from the  terminal to validate your solution to the exercise

**1.3.4 exercise-09: Delete the branch `feature`**

1. Execute the `git branch -D 'branch-name'` command to remove the `feature` branch from the previous exercises
    * `git branch -D feature`
2. This command removes a branch
3. Execute the: `npm run validate-exercise-09` command from the  terminal to validate your solution to the exercise

**1.3.5 exercise-10: Make a merge commit in the `master` branch from the develop branch**

1. You should be in the master branch before you continue with the next steps
2. Create a new file in the master branch named `exercise-10.txt` in the `src/exercises` folder that has any value inside
3. Create a new commit with the new file in the master branch
4. Make a new commit in the master branch that merges the commits from the develop branch with the command:
    * `git merge develop`
5. This will create a new merge commit with the commits from the develop and master branches
6. Execute the: `npm run validate-exercise-10` command from the  terminal to validate your solution to the exercise

### 1.4 Git Stashes (Extra Step)

**1.4.1 exercise-11: Create a new stash entry without a message**

1. Change the contents of the `exercise-03-a.txt` file and save the file
2. Run the GIT command to create a new stash entry without a message:
    * `git stash push`
3. This command will create a new stash entry with the changes that you made to the file.
4. Then you can use the `git stash list` command to see a list of all the stash entries that you made, or the the `git stash show stash@{0}` command to see the files that were affected by the stash entry number 0
5. Stash entries are 0 indexed like arrays
6. If you’d like to see the changes made in the stash you can use the following command to see the code changes in the stash entry: 
    * `git stash show --patch stash@{0}`
7. Execute the: `npm run validate-exercise-11` command from the  terminal to validate your solution to the exercise

**1.4.2 exercise-12: Remove the stash entry and apply the changes again**

1. Run the GIT command to remove the stash entry from the stash and apply the changes to the working directory
    * `git stash pop`
2. This command will remove the latest stash entry from the stash and apply the changes in the working directory.
3. Execute the: `npm run validate-exercise-12` command from the  terminal to validate your solution to the exercise

**1.4.3 exercise-13: Create a new stash entry with a message**

1. Create a new stash entry with the changes made to the `exercise-03-a.txt` file from the previous steps
2. Run the GIT command to create a new entry that has a message
    * `git stash push -m 'stash-message'`
3. Use a stash message of `'my stash message'`
4. This will create a new stash entry like the exercise-11 but one that has message that you define
5. Execute the: `npm run validate-exercise-13` command from the  terminal to validate your solution to the exercise

**1.4.4 exercise-14: Clear the stash list**

1. Run the GIT command to remove all the stash entries from the stash
    * `git stash clear`
2. This will remove all the stash entries from the stash
3. Execute the: `npm run validate-exercise-14` command from the  terminal to validate your solution to the exercise

**1.4.5 exercise-15: Create a new file and store it in a stash entry**

1. Create a new file named `exercise-15.txt` in the `src/exercises` folder and store any text value inside
2. Run the GIT command to create a new stash entry that also stashes files that are not tracked by GIT with a stash message of: `'stash with untracked files'`
    * `git stash push --include-untracked -m 'your message'`
3. Execute the: `npm run validate-exercise-15` command from the  terminal to validate your solution to the exercise

## Requirements

- You must perform all the steps using only the command line
- You must upload the repository with the exercises to your Github repository once you are finished
- You will have to learn how to connect to the Github platform using the terminal so that you can push the local repository

Before uploading the local repository with the exercise files to the remote repository you will need to:

- Create a new **empty** repository which you will use to push the exercise files
- Once you have created the empty repository, you should see a screen with the instructions of adding the remote url of the repository.
- Copy the `git remote add origin https://…` (this is your repository URL)
- Execute the following command to remove the existing remote origin of your local repository:
    * `git remote remove origin`
- You can execute the following command to see a list of the current remote URLs in your local repository:
    * `git remote -v`
- Add the remote repository URL from your GitHub as the new **origin** of your local repository
- Execute the following Git command to push the local repository
    * `git push --set-upstream origin master`
- The: `--set-upstream` command (or the shorthand version `-u`) sets the remote origin URL to be of type `tracking` so that the `git push`, `pull` and `fetch` commands use that remote URL as the default one

## Deliverables

The following deliverables will be necessary to evaluate the project:

- The repo uploaded to Github with the solutions of the exercises

## Resources

- [Official GIT](https://git-scm.com/)
- [Guide](https://rogerdudler.github.io/git-guide/)
- [Official practice guide](https://guides.github.com/activities/hello-world/)
- [Git Cheat sheet](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)
- [PRO GIT book](https://git-scm.com/book/en/v2)
- [Visual GIT guide](http://marklodato.github.io/visual-git-guide/index-en.html)
- [Learn GIT](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud)
- [Interactive graphical example GIT](https://git-school.github.io/visualizing-git/#free-remote)
- [Learn GIT](https://learngitbranching.js.org/)