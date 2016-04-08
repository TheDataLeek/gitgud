# The `.gitignore`

A `.gitignore` is a file that lives in the root of your project and tells git
what to track and what to ignore. It uses basic bash glob syntax, and it's
pretty straightforward to write.

```bash
# Ignore python files
*.py

# Ignore logfiles
*.log

# Ignore directory
./data*
```

# Dealing With Accidentally Adding the Wrong File

`git rm --cached badfile.txt`
