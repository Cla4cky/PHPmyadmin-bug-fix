# PHPmyadmin bug fix
- 今天重新安装phpmyadmin的时候遇到了一个bug： #2002 - No such file or directory &mdash; 服务器没有响应（或本地服务器的套接字没有正确设置）。一开始我还以为是我的mysql没打开或者apache配置错误，后来才发现问题是PHPmyadmin里面文件我没怎么配置。
       - 首先我们先去我们安装phpmyadmin的目录下，我的是mac所以可能和windows的配置有点不同，但是原理都是一样的！QWQ
       - 我们先找到<b>config.sample.inc.php</b>文件,我们用phpstorm打开（windows下可以用note++打开，不限制什么软件只要能修改就行了。）然后我们到第31行代码那，修改:<b>$cfg['Servers'][$i]['host']</b> =后面的''里面为127.0.0.1'(记得'是在英文键盘下的用中文的是不行的！）最后代码是：<b>$cfg['Servers'][$i]['host'] = '127.0.0.1'; </b>
       - 修改完了后我们先保存一下，然后我们再去phpmyadmin目录下的<b>libraries</b>文件夹里面找到<b>config.default.php</b>文件。我们和刚刚一样用phpstorm或者note++打开，然后我们来到第125行代码。我们和刚刚一样修改里面的<b>$cfg['Servers'][$i]['host']</b> =后面的''里面为127.0.0.1'。然后保存，现在我们重新去看看phpmyadmin是不是就能打开了^_^！
       
## PS:这里我的是最新的phpmyadmin如果你的是老版本的话可能配置和我的不是一样，其他版本的配置查询百度或者谷歌！

# powered by祭酒_Atin 
