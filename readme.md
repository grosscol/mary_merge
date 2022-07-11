# Mary Merge Conflict
A practice repo to illustrate fixing merge conflicts between branches.

## Setup
1. Clone repo

1. Change directory into project
```sh
cd mary_merge
```

## Examine Repository
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

## Merge Contributions
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

    Output should look similar to:
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

## Resolve Conflicts
Open lyrics.txt in a text editor.
Conflicts are indicated by chunks from each branch and are delimited with:
- `<<<<<<<`
- `=======`
- `>>>>>>>`

1. First conflict is the first two lyrics. Take blake_branch version.
    - delete everything from `<<<<<<< HEAD` to `=======`
    - delete `>>>>>>> blake_branch`
    - keep rest of black_branch content

1. Move on to next conflict

1. Next conflict is the remaining lyrics.
    Content from both blocks here hould be kept.
    HEAD block content only needs slight modifiation to delete the TODO left in.

    - delete `<<<<<<< HEAD` line.
    - delete `TODO` line as that isn't supposed to be in the lyrics
    - keep rest of HEAD block content as it is correct.

    - delete `=======` line
    - keep rest of blake_branch content as it is correct.
    - delete `>>>>>>> blake_branch`

1. Ensure single empty line between lyrics, and editting is done.
    At this point, the lyrics.txt file should have a complete and correct version of the poem.

1. Commit the resolution
    ```sh
    git add .
    git commit
    ```
    The commit will have a git supplied comment as it's the end of a merge:
    ```txt
    Merge branch 'blake_branch' into test
    ```

    Add an additional line to the commit message:
    ```txt
    Collate content and correct spacing.
    ```

1. Continue the merge
    In this case, the merge will be complete when you commit the resolution in the previous step.
    Otherwise you'd have to use `git merge --continue`
