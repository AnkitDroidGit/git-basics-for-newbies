# Git basics for newbies

Working with Github (or any software development version control using Git) for the beginners

Many new developers face this problem when they start working on a project which is shared among many team member and many of them need to work together on the project.
It becomes hard for newbies to create PR and adding their work to the upstream project repo.
I am trying to make this easier for all the newbies who are going to work on the project collaboration in the team.
By following these steps, it becomes easier to handle changes, stashing, committing, creating, and merging PR after approval.

Let's go through the steps with commands and sample project on Github.
For getting hands-on experience of the below steps, feel free to fork [this Github repo](https://github.com/AnkitDroidGit/git-basics-for-newbies) and follow along

1. Clone project from upstream to the local repo

   ```bash
        git clone git@github.com:AnkitDroidGit/git-basics-for-newbies.git
   ```

2. Open project with your favorite IDE/Code Editor
3. Pull the latest changes from upstream if you haven't pulled changes from quite some time (think of changes merged by other members of your team)

   ```bash
        git pull
   ```

4. Make your changes on master (default) branch. I am adding new file called `contributors.md` and appending it with my name `Ankit Kumar`.
5. Add file(s) to git for tracking by git add

   ```bash
        git add name
   ```

   You can add all files by running below command

   ```bash
        git add .
   ```

6. Check differences by running following command.

   ```bash
        git diff
   ```

7. Now suppose someone from your teams has already added and merged his changes to master branch. If you are going to commit and push your changes without synching repo with upstream, you might get conflicts that becomes hard to resolve later in case of many conflicts.
   Its great idea to sync your local repo with upstream.
   We will do it here by below commands.

   - First stash your changes. Stashing saves your working directory and index state WIP on master: with latest commit

     ```bash
         git stash
     ```

   - Run git pull for latest changes from upstream branch, if any.

     ```bash
         git pull
     ```

   - Apply your stashed change to active changelist or default changelist.

     ```bash
         git stash apply
     ```

8. Check your difference again by running git diff

   ```bash
       git diff
   ```

9. Resolve conflicts if any. Resolving conflicts now is easier compared to the time of many many conflicts at the time of creating PR without synching.
10. Now, add commit message

    ```bash
        git commit - m "added my name in contributors.md"
    ```

11. Checkout to new branch

    ```bash
        git checkout -b addedName
    ```

12. Push your changes to newly checked out branch. It will create a new branch on upstream with same name your have checked out with.

    ```bash
        git push --set-upstream origin addedName
    ```

13. Visit Github (or any software development version control using Git) repo on broswer.
    Click on `compare and pull request`,
    Write you PR name with appropriate comments.
    Add `reviewers` to request team members to review your PR.

14. Finally click on `create pull request`
    You have done your work already.
    Wait for the reviewer to review

15. Once PR is approved by the reviewer(s).
    Visit your branch and merge your branch.

16. On you local repo, pull master again before macking any other changes, follow the steps again.

### How to contribute

1.  Fork the project & clone locally and mentioned above.
2.  Create a branch, naming it either a suggetion: `git checkout -b suggetion/that-new-suggetion`
3.  Code and commit your changes. Bonus points if you write a [good commit message](https://chris.beams.io/posts/git-commit/): `git commit -m 'Add some suggetion'`
4.  Push to the branch: `git push origin suggetion/that-new-suggetion`
5.  Create a pull request for your branch 🎉
