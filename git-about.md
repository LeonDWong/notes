**reset**: Used for recall commit, combine with reflog, like `git reset --hard {yourreflog}`.

**rebase**: Used for recall previously commit log, be careful to use it once u had already pushed your newly commit to remote repository.

**revert**: Used for recall a specific commit, other commits which are before it or after it will not be affected. And the revert action will be a new commit.

**submodule**: It's helpful for user to using other repository in project. It can keep submodule updated time to time. Create by `git submodule add {repository address}`, pull by `git submodule init && git submodule update`， updated by `fetch` or `git submodule update`. But if you want your local change in submodule keep available for every remote update, you should use `git submodule update --remote --rebase`. Push local change by `git push --recurse-submodules=check`.