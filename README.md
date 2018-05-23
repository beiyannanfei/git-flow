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
    
    