# git-basics-for-newbies

Working with Github (or any software development version control using Git) for the beginners

Many new developers and face this problem when they start working on a project which is shared among many team member and many of them need to work together on the project.
It becomes hard for newbies to create PR and adding their work to the upstream project repo.
I am trying to make this easier for all the newbies who are going to work on the project collaboration in the team.
By following these steps, it becomes easier to handle changes, stashing, committing, creating, and merging PR after approval.

Let's go through the steps with commands and sample project on Github.
For getting hands-on experience of the below steps, feel free to fork [this Github repo](https://github.com/AnkitDroidGit/git-basics-for-newbies) and follow along

1. Clone project from upstream to the local repo

```
git clone git@github.com:AnkitDroidGit/git-basics-for-newbies.git
```

2. Open project with your favorite IDE/Code Editor
3. Pull the latest changes from upstream if you haven't pulled changes from quite some time (think of changes merged by other members of your team)

```
git pull
```

4. Make your changes on master (default) branch. I am adding new file called `name.md` and appending it with my name `Ankit Kumar`.
5. Add file(s) to git for tracking by `git add command`

```
git add name # this comamnd adds the one file at a time.
```

You can add all files by running below command

```
git add .
```

6. Check differences by running following command.

```
git diff
```

7. Now suppose someone from your teams has already added and merged his changes to master branch. If you are going to commit and push your changes without synching repo with upstream, you might get conflicts that becomes hard to resolve later in case of many conflicts.
   Its better to sync your local repo with upstream.
   We will do it here by below commands.
   - First stash your changes. Stashing saves your working directory and index state WIP on master: with latest commit
   ```
   gut stash
   ```
   - Run git pull for latest changes from upstream branch, if any.
   ```
   git pull
   ```
   - Apply your stashed change to active changelist or default changelist.
   ```
   git stash apply
   ```
   
