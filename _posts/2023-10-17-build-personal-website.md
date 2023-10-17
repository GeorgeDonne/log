
# 复制mm theme

~ % git clone git@github.com:GeorgeDonne/log.git gwlog
Cloning into 'gwlog'...
remote: Enumerating objects: 16950, done.
remote: Total 16950 (delta 0), reused 0 (delta 0), pack-reused 16950
Receiving objects: 100% (16950/16950), 44.33 MiB | 2.79 MiB/s, done.
Resolving deltas: 100% (10116/10116), done.
Updating files: 100% (743/743), done.

~ % cd gwlog
~/gwlog % git branch -av
* master                8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/HEAD   -> origin/master
  remotes/origin/dev    8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/master 8a67ce8e Improve PR close auto-comment message (#3713)

**在本地创建 dev 分支**

查看所有分支
~/gwlog % git branch -av
* master                8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/HEAD   -> origin/master
  remotes/origin/dev    8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/master 8a67ce8e Improve PR close auto-comment message (#3713)

查看本地分支和远程分支的对应关系
~/gwlog % git branch -vv
* master 8a67ce8e [origin/master] Improve PR close auto-comment message (#3713)

创建本地分支dev
查看所有分支。有了本地分支dev
查看本地和远程分支的对应关系。发现dev没有和远程分支对应起来
~/gwlog % git branch dev
~/gwlog % git branch -av
  dev                   8a67ce8e Improve PR close auto-comment message (#3713)
* master                8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/HEAD   -> origin/master
  remotes/origin/dev    8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/master 8a67ce8e Improve PR close auto-comment message (#3713)
~/gwlog % git branch -vv
  dev    8a67ce8e Improve PR close auto-comment message (#3713)
* master 8a67ce8e [origin/master] Improve PR close auto-comment message (#3713)

将本地分支dev和远程分支关联起来
查看对应关系。已对应起来了。
~/gwlog % git branch --set-upstream-to=origin/dev dev
branch 'dev' set up to track 'origin/dev'.
~/gwlog % git branch -vv
  dev    8a67ce8e [origin/dev] Improve PR close auto-comment message (#3713)
* master 8a67ce8e [origin/master] Improve PR close auto-comment message (#3713)

参考资料：
在Git中创建本地分支并关联远程分支；https://blog.csdn.net/yanwennian/article/details/133860421

切换到dev分支，开始工作……
~/gwlog % git switch dev
Switched to branch 'dev'
Your branch is up to date with 'origin/dev'.