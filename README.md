## 创建远程仓库  
**1.配置Git**
 * 首先再本地创建ssh key  
 
 `$ ssh-keygen -t rsa -C "your_email@youremail.com" `  
 （后面的your_email@youremail.com改为你在github上注册的邮箱，之后会要求确认路径和输入密码，我们这使用默认的一路回车就行。)
 
 * ~/下生成.ssh文件夹，打开id_rsa.pub，复制里面的key。
 * 回到github上，进入 Account Settings（账户配置），左边选择SSH Keys，Add SSH Key,title随便填，粘贴在你电脑上生成的key。
 * 验证是否连接成功  
 ` $ ssh -T git@github.com `  
 (如果是第一次的会提示是否continue，输入yes就会看到：You've successfully authenticated, but GitHub does not provide shell access 。这就表示已成功连上github。)

***

**2.连接本地仓库跟远程仓库**   
* 设置username/eamil  
 `$ git config --global user.name "your name"`   
 `$ git config --global user.email "your_email@youremail.com"` 
 
* 添加远程地址  
`$ git remote add origin git@github.com:yourName/yourRepo.git`  
（后面的yourName和yourRepo表示你再github的用户名和刚才新建的仓库，加完之后进入.git，打开config，这里会多出一个remote "origin"内容，这就是刚才添加的远程地址，也可以直接修改config来配置远程地址。）

  - 查看/修改github地址方法  
    > 默认是github的地址加上你的用户名  
      比如我的地址是https://github.com/chunqiuyiyu，其中chunqiuyiyu就是我的用户名
      打开github后，在右上角头像上点击会有“Your Profile”（如果你已经登录），点击进入的网页链接就是你的github地址，修改地址要进入“settings”修改用户名
    > 项目地址是github地址加上项目名称，  
      例子：https://github.com/chunqiuyiyu/learn-javascript

* 第一次提交本地文件  
 `mkdir learn_note` // 创建本地文件夹 => 进入本地文件夹再执行下一步  
`echo "# learn_notes" >> README.md` // 创建内容为# learn_notes"的README.md文件  
`git init` // 初始化本地仓库  
`git add README.md` // 添加文件  
`git commit -m "first commit"` // 提交说明  
`git remote add origin https://github.com/ceciFang/learn_notes.git` // 连接远程仓库  
`git push -u origin master` // 提交的master 分支

**3.远程仓库更新**
git add . // 提交所有文件
`git commit -m "xxx commit"` // 提交说明
`git remote add origin https://github.com/ceciFang/learn_notes.git` // 连接远程仓库  
`git pull --rebase origin master` // 本地仓库升级到最新版本
> 不能直接git pull
`git push -u origin master` // 提交的master 分支
