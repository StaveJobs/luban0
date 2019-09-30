# 解决Git远程仓库与本地仓库 冲突一（远程与本地 没有关联绑定）
项目需求：
    将本地master与远程origin/master进行关联（远程仓库中已经存在相同的项目，本地也创建项目，此时就会出现冲突）
    一般创建项目是从GitHub(远程仓库)中clone到本地，然后在打开项目，此时不会出现本文所说的冲突。Git会进行自动关联。

   操作步骤：
    1.将本地项目中的内容提交到本地仓库，进行管理。让git进行管理本项目
    2.将远程HEAD下载到本地
    3.将本地项目与远程项目关联
    4.将远程项目内容下载到本地
    5.将本地文件提交到远程（此时本地远程保持一致）

   实际操作操作步骤：

       1.将本地项目中的内容提交到本地仓库，进行管理。让git进行管理本项目
        git add -A
        git commit -m '本地项目添加入本地仓库，git管理此项目。'
       2.将远程HEAD下载到本地
        git fetch
       3.将本地项目与远程项目关联
        git branch --track --set-upstream-to=origin/master master
       4.将远程项目内容下载到本地
         git pull origin master --allow-norelated-histories
       5.将本地文件提交到远程（此时本地远程保持一致）
        git push origin master

