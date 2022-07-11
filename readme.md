# Mary Merge Conflict
A practice repo to illustrate fixing merge conflicts between branches.

## Guide

### Setup
1. Clone repo

1. Change directory into project
```sh
cd mary_merge
```

### Examine Repository
1. List branches
```sh
git branch
```

1. Examine log of current branch (main)
```sh
git log
```

1. Examine log of each user branch
```sh
git log blake_branch
git log avery_branch
```

### Merge Contributions
1. Create your own working branch from the main
Making a branch called resolution where you will do the work merging Blake and Avery's branch.
Doing work in branches helps keep the main branch clean.

```sh
git branch resolution
```
Checkout that branch
```sh
git checkout resolution
```

1. Merge Avery's changes into resolution branch
```sh
git merge avery_branch
```

Output should look like:
```txt
Updating f6e1979..68ae9dc
Fast-forward
 lyrics.txt | 17 ++++++++++++++++-
```

1. Examine log after merge
Observe how Avery's changes get applied on top of the commits already in the branch.
```sh
git log
```

1. Merge Blake's changes into resolution branch

```sh
git merge blake_branch
```

Output should look like:
```txt
Auto-merging lyrics.txt
CONFLICT (content): Merge conflict in lyrics.txt
Automatic merge failed; fix conflicts and then commit the result.
```

### Resolve Conflicts
Open lyrics.txt in a text editor.
Conflicts are indicated by chunks delimited with:
- `<<<<<<<`
- `=======`
- `>>>>>>>`

1.  See that the first line has a conflict between the branches.
    This line should be on two lines, and one editor has made that change while the other has not.
    Resolve this conflict by choosing the 

