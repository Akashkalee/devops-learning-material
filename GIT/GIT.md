# GIT

#### What is Git?
Git is a popular version control system. It was created by Linus Torvalds in 2025, and has been maintained by Junio Hamano since then.

Git is a tool that helps you :
    - save and manage different versions of your files and code.
    - work with others, keep track of changes, and undo mistakes.
#

#### Where to use GIT?
Git works on your computer, but you also use it with online services like Github, Gitlab, or Bitbucket to share your work with others. These are called remote respositories.
#

#### Why to learn Git?
- Git is widely used toll, across over 70% of developer use Git!
- It helps developers to work together from anywhere in the world.
- Developers can see the full history of the project.
- Developers can revert to earlier versions of a project. 
#

#### How to install Git
You can download Git for free from git-scm.com

- Windows: Download and run the installer.
  Click "Next" to accept the recommended settings.
  This will install Git and Git Bash.

- macOS: If you use Homebrew, open Terminal and type brew install git.
  Or, download the .dmg file and drag Git to your Applications folder.

- Linux: Open your terminal and use your package manager.
  For example, on Ubuntu: sudo apt-get install git
#

#### Verifying your installaton

After installing, check that git works by opening your terminal:
    ![alt text](image.png)

If Git is installed, you will see something like git version X.Y.Z
If you see an error, try closing and reopening your terminal, or check that Git is in your PATH.
#

#### Default Editor
During installation, Git asks you to pick a default text editor.

This is the program that will open when you need to write messages (like for commits).

![alt text](image-1.png)

If you're not sure, just pick the default (Notepad on Windows). You can always change this later.

![alt text](image-2.png)
#

#### Common Installation Issues
- "git is not recognized as an internal or external command"
    Solution: Git is not in your system's PATH. Make sure you installed Git and restart your terminal.
    If needed, add Git's bin folder (usually C:\Program Files\Git\bin) to your PATH.
    If it still doesn't work, try restarting your computer.
- Permission errors ("Permission denied")
    Solution: On Windows, run Git Bash or your terminal as administrator.
    On macOS/Linux, use sudo if necessary.
- SSL or HTTPS errors when cloning/pushing
    Solution: Check your internet connection.
    Make sure your Git version is up to date.
- Wrong version of Git
    Solution: Check your installed version with git --version.
    Download the latest version from git-scm.com if needed.
#

#### Configure Git

Configuring Git is safe.
You can change these settings at any time, they only affect how your name and email appear in your commits.
#

#### User Name

Your name will be attached to your commits. Set it with:

![alt text](image-3.png)
#

#### Email Address 

Your email is also attached to your commits. Set it with:

![alt text](image-4.png)

Change the user name and email to your own.

You will probably also want to use this when registering to GitHub later on.
#

#### Configuration Levels

There are three levels of configuration:
- System (all users): git config --system 
- Global (current user): git config --global
- Local (current repo): git config --local

The order of precendence is:

- Local (current repo)
- Global (current user)
- System (all users)

The reason to use the different levels is that you can set different values for different users or repositories.

This can be used for example to set different default branches for different repositories and users.
#

#### Creating Git Folder

![alt text](image-5.png)

Now we are in the correct directory and can initialize Git!
#

#### Initialize Git

Now that we are in the correct folder, we can initialize Git on that folder:

![alt text](image-6.png)

You just created your first Git Repository!
#

#### What is a Repository?
A Git repository is a folder that Git tracks for changes.
The repository stores all your project's history and versions:
#

#### What Happens When You Run git init?
Git creates a hidden folder called .git inside your project.
This is where Git stores all the information it needs to track your files and history.
#

#### What is a New File?
A new file is a file that you have created or copied into your project folder, but haven't told Git to watch.
#

#### What is an Untracked File?
An untracked file is any file in your project folder that Git is not yet tracking.
These are files you've created or copied into the folder, but haven't told Git to watch.
#

#### What is a Tracked File?
A tracked file is a file that Git is watching for changes.
To make a file tracked, you need to add it to the staging area.
#

#### What is the Staging Environment
The staging environment(or staging area) is like a waiting room for your changes.
You use it to tell Git exactly which files you want to include in your next commit.
This gives you control over what goes into your project history.

Here are some key commands for staging:
- git add <file> -Stage a file.
- git add --all or git add -A -Stage all changes
- git status -See what is staged.
- git restore --staged <file> -Unstage a file
#

#### Stage a File with git add

To add a file to the staging area, use git add <file>:

![alt text](image-7.png)
#

#### Stage Multiple Files

You can stage all changes (new, modified, and deleted files) at once:

![alt text](image-8.png)

git add -A does the same thing as git add --all.
#

#### Check Staged Files with git status

See which files are staged and ready to commit:

![alt text](image-9.png)
#

#### How to Unstage a File

If you staged a file by mistake, you can remove it from the staging area (unstage it) with:

![alt text](image-10.png)

Now index.html is no longer staged. You can also use git reset HEAD index.html for the same effect.
#

#### Git Commit 

#### What is Commit?
A commit is like save point in your project.

It records a snapshot of your files at a certain time, with a message describing what changed.
You can always go back to a previous commit if you need to.

Here are some key commands for commits:
git commit -m "message" - Commit staged changes with a message
git commit -a -m "message" - Commit all tracked changes (skip staging)
git log - See commit history
#

#### How to Commit with a Message (-m)

To save your staged changes, use git commit -m "your message":

#
#### Commit All Changes Without Staging (-a)

You can skip the staging step for already tracked files with git commit -a -m "message".

This commits all modified and deleted files, but not new/untracked files.

![alt text](image-11.png)
#

#### Write Multi-line Commit Messages

If you just type git commit (no -m), your default editor will open so you can write a detailed, multi-line message:

![alt text](image-12.png)
#

#### Commit Message Best Practices:
- Keep the first line short (50 characters or less.)
- Use the imperative mood (e.g., "Add feature" not "Added feature").
- Leave a blank line after the summary, then add more details if needed.
- Describe why the change was made, not just what changed.
#

#### Other Useful Commit Options
- Create an empty commit:
    git commit --allow-empty -m "Start Project"
- Use previous commit message (no editor):
    git commit --no-edit
- Quickly add staged changes to lat commit, keep message:
    git commit --amend --no-edit
#

#### Troubleshooting Common Commit Mistakes
Forgot to stage a file?
If you run git commit -m "message" but forgot to git add a file, just add it and commit again. Or use git commit --amend to add it to your last commit.
Typo in your commit message?
Use git commit --amend -m "Corrected message" to fix the last commit message.
Accidentally committed the wrong files?
You can use git reset --soft HEAD~1 to undo the last commit and keep your changes staged.
#

#### View Commit History (git log)
To view the history of commits for a repository, you can use the git log command:

![alt text](image-13.png)


For a shorter view, use git log --oneline:

![alt text](image-14.png)

To see which files changed in each commit, use git log --stat:
#

#### Git Tagging

#### What is a Tag?
A tag in Git is like a lebel or bookmark for a specific commit.

Tags are most often used to mark important points in your projects history, like releases(v1.0 or v2.0)

Tags are a simple and reliable way to keep track of versions and share then with your team or users.

Some common tag types include:
    - Release: Tags let you mark when your project is ready for release, so you (and others) can always find that exact version later.
    - Milestone: Use tags to highlight major milestones, like when a big feature is finished or a bug is fixed.
    - Deployments: Many deployment tools use tags to know which version of your code to deply.
    - Hotfixes: If you need to fix an old version, tags make it easy to check out and patch the right code.
#

#### Key Commands for Tagging

    git tag <tagname> -Create a lightweight tag
    git tag -a <tagname> -m "message" -Create an annotated tag
    git tag <tagname> <commit-hash> -Tag a specific commit
    git tag -List tags
    git show <tagname> -Show tag details
#

#### Create a Lightweight Tag

A lightweight tag is just a name for a commit.
It's quick and simple, but does not store extra information.

#### Annotated vs Lightweight Tags
    - Annotated Tag: Stores author, date, and message.
    Recommended for releases and sharing with others.
    - Lightweight Tag: Just a simple name for a commit(no extra info, like a bookmark).

#### Create an Annotated Tag (-a -m)

An annotated tag stores your name, the date, and a message.
This is recommended for most uses.

![alt text](image-16.png)

#### Tag a Specific Commit

You can tag an older commit by specifying its hash:

![alt text](image-15.png)


#### List Tags

See all tags in your repository:

![alt text](image-17.png)

#### Show Tag Details (git show)

See details about a tag and the commit it points to:

![alt text](image-18.png)

#### Push Tags to Remote

By default, tags exists only on your local computer.
If you want others to see your tags, you need to push them to your remote respository.
If you don't push your tags, only you will see them, and only locally.
To push a single tag to your remote repository (for example, after creating a release tag):

Did you know? Pushing commit with git push does not push your tags!

You must push tags explicitly as shown above.

To push all your local tags to the remote at once (useful if you've created several tags):

![alt text](image-19.png)

#### Delete Tags

Delete a tag locally:

![alt text](image-20.png)


Delete a tag from the remote repository:

![alt text](image-21.png)

#### Update or Replace a Tag (Force Push)

If you need to move a tag to a different commit and update the remote, use --force:

![alt text](image-22.png)

#### Tagging best Practices

- Use tags to mark releases, major milestones, or stable points in your project.
- Always use annotated tags (with -a -m) for anything public or shared.
- Create tags after passing all tests or before deploying/releasing code.

#### Git Stash

