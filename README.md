# git-flow

    1. 首先执行初始化(注意: 保证本地没有未提交的修改，否则报错)
    
```
    ➜  git-flow git:(develop) git flow init
    Fatal: Working tree contains unstaged changes. Aborting.
    ➜  git-flow git:(develop) ✗ git flow init
    
    Which branch should be used for bringing forth production releases?
       - develop
       - master
    Branch name for production releases: [master] 
    
    Which branch should be used for integration of the "next release"?
       - develop
    Branch name for "next release" development: [develop] 
    
    How to name your supporting branch prefixes?
    Feature branches? [feature/] 
    Bugfix branches? [bugfix/] 
    Release branches? [release/] 
    Hotfix branches? [hotfix/] 
    Support branches? [support/] 
    Version tag prefix? [] 
    Hooks and filters directory? [/Users/wyq/bynf/git-flow/.git/hooks] 

```

    2. 开发新功能(基于develop分支)
    
```
    ➜  git-flow git:(develop) git flow feature start myfeature
    Switched to a new branch 'feature/myfeature'
    
    Summary of actions:
    - A new branch 'feature/myfeature' was created, based on 'develop'
    - You are now on branch 'feature/myfeature'
    
    Now, start committing on your feature. When done, use:
    
         git flow feature finish myfeature

```
    执行 git flow feature start myfeature 后会创建一个 feature/myfeature 的分支，并切换到该分支
    之后便可以在这个分支做相应修改。
    
    修改完成后执行 git flow feature finish myfeature 后会将 feature/myfeature 分支合并到 develop 分支，
    并删除 feature/myfeature 分支，最后切换回 develop 分支.

```
    ➜  git-flow git:(feature/myfeature) git flow feature finish myfeature
    Switched to branch 'develop'
    Your branch is up to date with 'origin/develop'.
    Updating 6c4fced..7aa50b4
    Fast-forward
     README.md | 18 ++++++++++++++++++
     1 file changed, 18 insertions(+)
    Deleted branch feature/myfeature (was 7aa50b4).
    
    Summary of actions:
    - The feature branch 'feature/myfeature' was merged into 'develop'
    - Feature branch 'feature/myfeature' has been locally deleted
    - You are now on branch 'develop'

```
    
    如果需要合作开发一个新功能，可以将新分支发布到远端
    
```
    ➜  git-flow git:(feature/myfeature) git flow feature publish myfeature
    Counting objects: 3, done.
    Delta compression using up to 4 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 365 bytes | 365.00 KiB/s, done.
    Total 3 (delta 2), reused 0 (delta 0)
    remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
    To github.com:beiyannanfei/git-flow.git
     * [new branch]      feature/myfeature -> feature/myfeature
    Branch 'feature/myfeature' set up to track remote branch 'feature/myfeature' from 'origin'.
    Already on 'feature/myfeature'
    Your branch is up to date with 'origin/feature/myfeature'.
    
    Summary of actions:
    - The remote branch 'feature/myfeature' was created or updated
    - The local branch 'feature/myfeature' was configured to track the remote branch
    - You are now on branch 'feature/myfeature'

```    

    取得其它用户发布的新特性分支，并签出远程的变更
    
```
    ➜  git-flow git:(develop) git flow feature pull origin myfeature
    The command 'git flow feature pull' will be deprecated per version 2.0.0. Use 'git flow feature track' instead.
    Created local branch feature/myfeature based on origin's feature/myfeature.

```    
    