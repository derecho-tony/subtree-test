subtree-test
============

> This github project documents and tests synchronization of git repos and repo dependencies

### To add a dependency

```sh
git remote add homieg_remote https://github.com/derecho-tony/homieg.git
git fetch homieg_remote
git checkout -b homieg_branch homieg_remote/master
git checkout master
git read-tree --prefix=homieg/ -u homieg_branch
git commit -m 'added homieg subtree'
```

### To check if dependencies have updates

```sh
git fetch homieg_remote
git diff-tree -p homieg_remote/master
```

#### if there are differences...

```sh
git checkout homieg_branch
git subtree pull --prefix=homieg homieg_remote master
```

#### it's likely that automatic merge will fail, so we'll have to do it manually

```sh
git mergetool
git commit
git status
git push
```

#### Outstanding Questions
- How do we know what version of the remote repo a subtree is at?
- What is the process for updating the subtree in the disconnected gitrepo?
