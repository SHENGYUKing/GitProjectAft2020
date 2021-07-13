# GitProjectAft2020

2020年以后正确Git项目到GitHub的姿势    

## 是什么

这是一个很无奈的说明性文档便于记录在2020年以后如何正确Git自己的项目到GitHub    

## 为什么

美丽国因为政治正确需要致使计算机业界多年的传统都将被强行更替，不能谓之错但改变的契机着实恶臭，也许这就是所谓的拘小礼而失大义吧：)    

## 怎么做

传统步骤：    

1. 初始化工程：在需要Git的项目文档根目录中启动Git Bash

   git init    

2. 添加文件：添加需要Git的项目文件，全部即为“.”

   git add .    

3. 预提交：“”中间的内容是自定义注释

   git commit -m "balabalabala"    

4. 关联到远程仓库：事先需要在GitHub本站建立新的仓库

   git remote add origin "https://github.com/......"    

5. 拉取相关文件：以防止强制提交导致仓库初始化文件丢失

   git pull --rebase origin master    

6. 完成提交：

   git push -u origin master    

现在需要在上述步骤5,6的基础上进行调整，因为这里出现了“master”，对就是那个表示主从的“master”，调整之后的相关步骤为：    

5. 切换分支：切换当前分支到“main”

   git checkout -b main    

6. 检查是否切换成功：显示中星号在“main”前面就对了

   git branch    

7. 合并分支：

   git merge master    

8. 拉取原分支上的文件：因为本地分支实际默认为“master”远程为“main”所以这里要解除历史关联

   git pull origin main --allow-unrelated-histories    

9. 完成提交：这里可能出现SSL问题(10054)，可以参考步骤10解决

   git push origin main    

10. 出现“SSL SSL_read: Connection was reset, errno 10054”此时可以先运行：
    git config --global http.sslVerify "false"

    之后再进行步骤9尝试应该就能够成功上传
