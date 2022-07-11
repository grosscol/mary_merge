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

### Merge and Resolve Conflicts
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

1. Examine log after merge
Observe how Avery's changes get applied on top of the commits already in the branch.
```sh
git log
```

2. Merge Blake's changes into resolution branch

```sh
git merge blake_branch
```
