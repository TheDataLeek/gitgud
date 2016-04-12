# Branches: Let's get Fancy

Now that you've impressed your friends with your git skillz, time to up the ante. Let's talk about Branches.

A branch is (like I said before) just a fork of your repository that's kept in the same spot.

## Branches: Why do we care?

Let's say your term paper is coming along nicely about the socio-economic status of whales in the pacific ocean, and you
want to include details on the impact of hurricanes, but you aren't sure it will be a good fit for the paper. Let's say
you'd have to delete a large portion of your paper in order to make it fit well. This is where branches save the day.

A branch lets you completely change everything, and then decide to either keep the changes, or throw them away.

## Branches: Pls How?

By default, when you're using git, you are editing and making changes in the `master` branch. (remember when we used
`push -u origin master`?) To make a new branch, type

```bash
git checkout -b hurricanes
```

This creates a new branch called `hurricanes` with a copy of all of the code from your last commit and automatically
switches you over to it.

To list all branches, type

```bash
git branch
```

To switch to a different branch, first `add` all files and `commit` all changes, and then type `git checkout master`.
(or whatever branch you want to switch to)

When you've decided that talking about the hurricanes was a good call, it's time to merge your changes with the master
branch.

```bash
git checkout master
git merge hurricanes
git push -u origin master
```

This will take the current state of the `hurricanes` branch and overwrite the `master` branch with its contents. Lastly,
it will upload your new master branch to github.

## Alternate Syntax

If you want to create a branch from a different branch than the one you're currently residing in, use the following
syntax.

```bash
git checkout -b $NEWBRANCHNAME $OLDBRANCHNAME
```

## No Fast Forward

If you've created a branch from master, made some changes, and are merging it back with master, you can add the
`--no-ff` flag to merge to prevent the `HEAD` pointer from just fast-forwarding (moving the pointer) and instead keep
the fact that the branch was created.
