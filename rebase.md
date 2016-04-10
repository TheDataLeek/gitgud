# Rebasing

[Here's the official documentation on
rebasing.](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)

Rebasing is a really really awesome way to change the history of your commits.
Rebasing is like merging, as it combines commits, but instead of adding them to
your tree, it combines commits. I use this mostly for the command

```bash
git rebase -i HEAD~3
```

Which will take the last (in this case) 3 commits and rebase however I see fit.
If you run this command, you'll be prompted with an editor window where you can
`pick` a commit to keep, and `squash` all others into it. At the end of this
process you'll be left with 1 (or however many you left) commit that will have
all of the combined changes in a single commit.

There are a ton of upsides and downsides to this strategy, the most notable
downside however is that you lose all history of changes that have been made.

You also have to be careful about rebasing after a push. Let's say you have 5
commits, and you're not happy with having a bunch of little commits, and you
want to put them all together. If you've already pushed up to a remote git repo,
then after you rebase and try to push, it will complain that you're missing
changes. The *only* fix for this at this point is to just

```bash
git push -fu origin master
```

Which forces a push, and forcibly overwrites your previous commit history.

**So here's a word of warning**

Rebasing is super sexy, but *don't do it if you've already pushed.*
