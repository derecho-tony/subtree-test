subtree-test
============

> This github project documents and tests synchronization of git repos and repo dependencies

### Steps?

```sh
git remote add homieg_remote https://github.com/derecho-tony/homieg.git
git fetch homieg_remote
git checkout -b homieg_branch homieg_remote/master
git checkout master
git read-tree --prefix=homieg/ -u homieg_branch
git commit -m 'added homieg subtree'
```
