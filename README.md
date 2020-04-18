## 创建远程仓库  
**1.配置Git **   
 *首先再本地创建ssh key  
 $ ssh-keygen -t rsa -C "your_email@youremail.com"  
 （后面的your_email@youremail.com改为你在github上注册的邮箱，之后会要求确认路径和输入密码，我们这使用默认的一路回车就行。成功的话会在~/下生成.ssh文件夹，进去，打开id_rsa.pub，复制里面的key。）
 * 回到github上，进入 Account Settings（账户配置），左边选择SSH Keys，Add SSH Key,title随便填，粘贴在你电脑上生成的key。
 * 验证是否连接成功  
  $ ssh -T git@github.com //
  
  
 


echo "# learn_notes" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/ceciFang/learn_notes.git
git push -u origin master

