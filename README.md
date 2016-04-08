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
* A pull request is a happy little message asking someone to incorporate your code into theirs. Sometimes shortened to
  "PR".
* A branch is basically a fork of your code that lives in the same repository.

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

And honestly, this is good enough. There's a ton more you can do with git, but that's the basic idea. If you stop
reading here, you are good to go. If you want to learn more, keep reading.

1. ["Uh oh I messed up"](./uhoh.md)
2. [Branches](./branches.md)
3. [Tracking Files](./filetracking.md)
4. [Collaboration](./collab.md)

# Git for Non-Scrubs

I bet you disagree with me on almost every point, and yeah, I deserve some of that. I don't use git the way Linus
Torvalds uses git. I don't use git the way that you probably use git. I take some shortcuts, and my commit messages
aren't always little special snowflakes. But you know what? It's good enough. This let's me use the basics without
~~any~~much of the cruft.

Feel free to make issues on here if you really really can't stand the way I've written this.

I'll just be happy if I never have to do backups with directories again (like I was forced to for a certain job which
will not be named).
