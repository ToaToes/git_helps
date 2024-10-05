# git_helps
some useful hints for git incase brain dead
![alt text]( https://github.com/ToaToes/git_helps/blob/main/MgaV9.png)


## Repository Initialize
</br> If you intended to start a new repository in this directory, you can initialize it with:
```
git init
```


## Clone an Existing Repository: 
</br>If you meant to work with an existing repository, you might need to clone it from GitHub or another source. You can do this with:
```
git clone <repository-url>
```
### git clone can potentially override local files if you try to clone a repository into a directory that already contains files. 
</br>Empty Directory: If you clone a repository into an empty directory, it will copy all the files and commit history from the remote repository into that directory without issues.
</br>Non-Empty Directory: If you attempt to clone a repository into a directory that already has files, Git will not allow it and will display an error message:

</br>1. Clone into a New Directory: Specify a new directory name when cloning:
```
git clone <repository-url> new-directory-name
```
</br>2. Move Existing Files: If you want to clone into a specific directory that already contains files, you can:
</br>Move the existing files to another location.
</br>Clone the repository into that directory.
```
mv existing-file.txt /path/to/backup/
git clone <repository-url> existing-directory
```
</br>3. Pull Changes Instead: If you already have a local repository and want to update it with changes from the remote repository, use:
```
git pull
```


## Check Remote Repository: 
</br> Ensure your local repository is linked to the correct GitHub repository. You can check this with:
```
git remote -v
```
This will list the remote repositories associated with your local repo.


## Stage all changes:
```
git add .
```
stage selected files:
```
git add [filename1] [filename2]
```


## Commit changes: 
</br> Commit the staged changes with a descriptive message:
```
git commit -m "Your commit message here"
```


## "Your branch is ahead of 'origin/main' by 1 commit."
</br> means that you have made a commit in your local repository that hasn't been pushed to the remote repository on GitHub
</br> 
</br> unsure whether other changes have been made on the remote since your last pull, you might want to fetch updates first:
```
git fetch origin
```


## Cancel the commit / Reset commit 
</br> To remove the last commit but keep the changes in your working directory:
```
git reset 
```
If you want to discard the last commit and its changes entirely:
```
git reset --hard [HEAD~1]
```

</br> Then create a new commit
## Push the Changes: Finally, push the updated commit to the remote repository:
```
git push origin main --force
```
The --force option is necessary here because you have rewritten history by removing the previous commit. Be cautious when using --force, especially if others are also working on the same branch.

## Example
```
# Reset the last commit but keep changes
git reset HEAD~1

# Make your changes to the files

# Stage the changes
git add .

# Commit the changes with a new message
git commit -m "Your new commit message here"

# Push the changes to the remote repository
git push origin main --force
```



## Push Changes to GitHub:
</br> Push your committed changes to the specific GitHub repository. If you want to push to the main branch (or any other branch), use:
```
git push origin main
```
Replace main with the name of the branch you're working on if it's different.


## Branching: 
</br> If you want to commit to a branch other than main, ensure you're on that branch by using:
```
git checkout [branch-name]
```
Create a New Branch (Optional): If you want to work on a new branch before pushing:
```
git checkout -b [new-branch-name]
```
Example: 
```
cd path/to/your/local/repo
git remote -v                  # Check remote repository
git add .                      # Stage all changes
git commit -m "Add new feature" # Commit changes
git push origin main          # Push to the main branch on GitHub
```

