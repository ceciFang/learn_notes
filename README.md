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
 
**2.连接本地仓库跟远程仓库**   
***
* 设置username/eamil  
 `$ git config --global user.name "your name"`   
 `$ git config --global user.email "your_email@youremail.com"` 
 
* 添加远程地址  
`$ git remote add origin git@github.com:yourName/yourRepo.git`
（后面的yourName和yourRepo表示你再github的用户名和刚才新建的仓库，加完之后进入.git，打开config，这里会多出一个remote "origin"内容，这就是刚才添加的远程地址，也可以直接修改config来配置远程地址。  
创建新文件夹，打开，然后执行 git init 以创建新的 git 仓库。）
***
echo "# learn_notes" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/ceciFang/learn_notes.git
git push -u origin master

