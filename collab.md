# Pull Requests

So let's say that your term paper is super awesome, and your friend wants to help you with it (our metaphor is
breaking). They can "fork" (read: copy) your repository, make a bunch of changes with their version, and then submit a
pull request through github. You'll get a nice little message saying something like "Please let me add this to your code
it fixes everything" and you can accept the changes, reject the changes, or ask them for some more work on it for it to
be approved. Once you click accept, all the work they've done will merge with your code in the exact same way branches
merge.

Take a look at this repository and checkout the "Pull requests" tab to see an example.

# Fetching Upstream Changes

This part is especially important for those of you that want to really bite into open source development and want to
contribute to some *awesomesuperspecial* package that you're excited about. Let's say you submitted a pull request a
while back, but a ton of changes have happened since then and your fork is now out of date.

First add the "upstream" (read: original) repository to your list of remotes (take a look at the next section for more
on remotes).

```bash
git remote add upstream <url>
```

Now pull the changes down to their own local branch.

```bash
git fetch upstream
```

Lastly, merge the upstream changes with your branch.

```bash
git merge upstream/master
```

[Github has a page on this too.](https://help.github.com/articles/syncing-a-fork/)

# Remotes (for the curious/ambitious)

Remember that command above where I typed `git remote add origin <url>`? Let's dissect that a little.

A `remote` is basically a fancy word for a spot on a server to store your code. You can have any number of remotes.

```bash
git remote -v
```

This command will list all remotes you've set for the repository

```bash
git remote -d origin
```

Will delete the remote called `origin`.

# Commit Messages

There are a ton of thoughts/blogs on writing good commit messages. Mine are short, and try to cover the basics.
Sometimes I just use something like `"backup hopefully fixing everything"`, which is admittedly bad, but whatever works
for you is good.

That being said, if you're working on a big open source project, you better hope your commit messages are up to their
standards.

[Check here for more discussion on crafting the perfect commit message.](http://bfy.tw/57E8)

