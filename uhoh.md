# "Uh oh I messed up"

So git comes with a couple helpful tools to see what went wrong. Let's go over these.

## Git Status

`git status` will tell you what the current situation is with your repository. It will let you know what's changed since
your last commit, what's being tracked, etc.

```bash
$ git status

Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

## Git Log

`git log` will list the last commits. `git log -p` will list the last several commits and show the changes between
commits. Don't always use this, because if you make a ton of changes it will be useless info.

```bash
$ git log -n 2

On branch master
commit 75627a80f802eb8072c1f49ef4c501137379c5c1
Merge: 372a040 a97361f
Author: Will F <willzfarmer@gmail.com>
Date:   Tue Apr 5 16:27:00 2016 -0600

    Merge pull request #8 from willzfarmer/pullrequests
    
    Added section on PR

commit a97361f4e2a091e512958cc3b89acf6f4b873881
Author: William Farmer <willzfarmer@gmail.com>
Date:   Tue Apr 5 16:26:03 2016 -0600

    Added section on PR
```

## "None of those worked pls halp"

![https://xkcd.com/1597/](https://imgs.xkcd.com/comics/git.png)

