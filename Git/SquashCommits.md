# How To 
## Squash git commits

* Squash with a new commit message

  ```shell
  # squashes the last 3 commits (HEAD~3)
  
  # bash
  git reset --soft HEAD~3 && 
  git commit -m "<New Commit Message>"

  # powershell
  git reset --soft HEAD~3; git commit -m "<New Commit Message>"
  ```

* Squash with previous commit messages included in the new commit message

  ```shell
  # bash
  git reset --soft HEAD~3 &&
  git commit --edit -m "$(git log --format=%B --reverse HEAD..HEAD@{1})"

  # powershell
  git reset --soft HEAD~3; git commit --edit -m "$(git log --format=%B --reverse 'HEAD..HEAD@{1}')"
  ```

### Ref

* [StackOverflow - Squash my last X commits together using Git](https://stackoverflow.com/questions/5189560/squash-my-last-x-commits-together-using-git/5201642#5201642)