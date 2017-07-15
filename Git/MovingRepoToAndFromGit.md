# How To
## Move an existing git repo from one hosting service to another

```shell
# Goto local repo path
cd path/to/repo

# Rename the existing remote to any name
# Here origin is renamed to oldorigin
git remote rename origin oldorigin

# Add the new origin using the new repository url
git remote add origin https://new/repo/url

# Push the current commits to the new remote's 'master' branch
git push origin master

# Remove the old remote
git remote rm oldorigin
```

### Ref

* [GitHub Gist](https://gist.github.com/mandiwise/5954bbb2e95c011885ff)