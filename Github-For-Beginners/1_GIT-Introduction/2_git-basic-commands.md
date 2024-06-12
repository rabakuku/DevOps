# Git Basic Commands

### HELP

```
git help

start a working area (see also: git help tutorial)
   clone      Clone a repository into a new directory
   init       Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add        Add file contents to the index
   mv         Move or rename a file, a directory, or a symlink
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect     Use binary search to find the commit that introduced a bug
   grep       Print lines matching a pattern
   log        Show commit logs
   show       Show various types of objects
   status     Show the working tree status

grow, mark and tweak your common history
   branch     List, create, or delete branches
   checkout   Switch branches or restore working tree files
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   merge      Join two or more development histories together
   rebase     Reapply commits on top of another base tip
   tag        Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch      Download objects and refs from another repository
   pull       Fetch from and integrate with another repository or a local branch
   push       Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
```

### init

```
#Create an empty Git repository or reinitialize an existing one
git init
touch story1.txt
echo "This is a beautiful story" >> story1.txt

```

### Status

```bash
#Show the working tree status
git status

#the default branch
On branch master

#we have not saved it to the repo
No commits yet

#files that are not tracked and git does not know where to go
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	story1.txt

nothing added to commit but untracked files present (use "git add" to track)

```

### ADD - Staging Area

```
#Add file contents to the index
git add story1.txt

#will stage all files in the directory
git add .
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/K8E1g51y8DFO3nZw-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/K8E1g51y8DFO3nZw-image.png)

### COMMIT

```
#Save Changes to the online repo
git commit -m "Added First Story"

```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/tAFqdzeygDM7RXNc-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/tAFqdzeygDM7RXNc-image.png)

### USER

```
#git user who will be the owner of the commit.
#Set git username as sarah and user email as sarah@example.com using the below commands.

git config user.email sarah@example.com
git config user.name sarah

```

### GitIgnore

```
It is good that the file is untracked. But it is still under GIT's radar. If you run the "git add ." command accidentally git will start to track this file.
Let's configure git to ignore this file permanently.

Add the file to a .gitignore file. 
echo notes.txt >> .gitignore
```

### GITLOG

```
#shows all the commit and changes made to the repo
git log
commit 2c779fb31263ba7d5f99db9e05359a7eb7173755 (HEAD -> master)
Author: raba <raba@pop-os.localdomain>
Date:   Mon Jun 10 21:18:59 2024 -0400

git log --oneline
2c779fb (HEAD -> master) Added First Story


cd /home/sarah/story-blog; git log


#You can list the changed files as well using the --name-only option with the git log command
git log --name-only

```