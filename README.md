# Git for Scrubs

[Scrub: Definition](http://www.urbandictionary.com/define.php?term=scrub)

>  A scrub is a now generalized term used as a synonym for a "noob" or "newb," which is someone who is bad at a video
>  game or activity in general. 

So you're a git scrub. It's ok. We all started there. Let's fix that.

(Disclaimer: If you're not a git scrub and reading this, I use a lot of simplified syntax to make lives easier. "But
it's not perfectly correct!" you cry. I don't care. I'm doing this to help people. I don't care about making it 100%
Linus Certified.)

## What is git?

Git is a way to keep track of things. It's a way for you to make sure you don't lose your files as well as keep track of
how your files have changed. That's it. There's some fancy stuff that we'll cover too, but at its core git is just
trying to make your life easier.

## Why do we need git?

Here's a simple example of the problem that git solves.

```bash
$ find .

.
./finalpaper.docx
./finalpaper1.docx
./finalpaper121.docx
./finalpaper-final.docx
./finalpaper-final_REAL.docx
./finalpaper-THISONEISWEAR.docx
```

This is terrible. This is the solution for git scrubs. Don't be a git scrub.

## Terminology

* A repository is a place where git keeps things. This can either be on your computer, or on a site like github.
* A commit is a bunch of changes balled up together and applied at once. It's kinda like a version, but not as formally
  defined.
* A fork is a copy of someone else's repository that you can edit.
* A pull request is a happy little message asking someone to incorporate your code into theirs.
* A branch is basically a fork of your code that lives in the same repository. (we'll go over this later)

## The Basics

Let's say you want to track your term paper in git. How do we do this? Well, it's simple.

```bash
git init
git add termpaper.docx
git commit -m 'Initial Commit'
```

Let's go over this line by line.

```bash
git init
```

This tells git to start tracking the current directory that you're in.

```bash
git add termpaper.docx
```

This tells git to start keeping track of that file. Initially git won't track anything, so you have to tell it what to
look at.

```bash
git commit -m 'Initial Commit'
```

This tells git to make a "verson", or commit, with the message attached saying "initial commit".

## Github

Now let's say you're paranoid about losing your work. This is where github comes in. Github is just a really really
fancy server to store git repositories. Let's store our term paper on their site. Go make an account, and then make a
new repository. (I'm not gonna guide you through this part. Google it.)

Once you have your repository, we can "push" (read: upload) our code to it.

```bash
git remote add origin https://github.com/willzfarmer/termpaper
git push -u origin master
```

The first line is responsible for telling git where to upload the code, and the second tells git to push the "master"
branch to the "origin" repository.

(Clever cookies will note that while we called the place to put our code "origin", we could also just as easily call it
something like "bestserverever")

## Everyday Use

K, you are now no longer a scrub. Here's a basic workflow.

1. Make a bunch of changes to a bunch of files.
2. `git add -A` adds every file in the current directory (and deletes files that are no longer present from the
   repository)
3. `git commit -m 'im the best coder evarrrr'` makes a new commit for the changes that you've made.
4. `git push -u origin master` uploads your code to github.
5. Go back to 1.

(This is actually my workflow for 90% of my projects on github)

## "Uh oh I messed up"

![Solution](https://imgs.xkcd.com/comics/git.png)

## Let's get Fancy

Now that you've impressed your friends with your git skillz, time to up the ante. Let's talk about Branches.

A branch is (like I said before) just a fork of your repository that's kept in the same spot.

### Branches: Why do we care?

Let's say your term paper is coming along nicely about the socio-economic status of whales in the pacific ocean, and you
want to include details on the impact of hurricanes, but you aren't sure it will be a good fit for the paper. Let's say
you'd have to delete a large portion of your paper in order to make it fit well. This is where branches save the day.

A branch lets you completely change everything, and then decide to either keep the changes, or throw them away.

### Branches: Pls How?

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
