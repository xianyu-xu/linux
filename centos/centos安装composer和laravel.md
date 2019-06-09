1.wget https://dl.laravel-china.org/composer.phar -O /usr/local/bin/composer
chmod a+x /usr/local/bin/composer
2.查看composer 是否安装

 3.composer global require "laravel/installer"

   4.请确定你已将 /root/.config/composer/vendor/bin 路径加到 PATH，只有这样系统才能找到 laravel 的执行文件。

　  一旦安装完成，就可以使用 laravel new 命令在指定目录创建一个新的 Laravel 项目，例如：laravel new blog 将会在当前目录下创建一个叫 blog 的目录，此目录里面存放着新安装的 Laravel 和代码依赖。这个方法的安装速度比通过 Composer 安装要快上许多：

  laravel new blog

注:1.查看 path  : echo $PATH
　 2.添加到path里面 :export PATH=$PATH:/root/.config/composer/vendor/bin (可以先find 一下，添加正确的地址)
   3.执行 source /etc/profile 使配置生效
   4.如果出现如下错误：可以 cd /root/.config/composer/vendor/laravel/installer 到这个目录下面,对laravel这个目录进行授权 chmod a+x laravel
　　
   5.如果出现如下错误，就是php.ini 里面没有开启服务，找到proc_open, 在disable_functions变量里面，删除该函数即可，重启php-frm(php version 7.1.5)
   

CentOS查看和修改PATH环境变量的方法
2018年11月12日 09:46:53 IvenOne 阅读数：1838
查看PATH：echo $PATH
以添加mongodb server为列
修改方法一：
export PATH=/usr/local/mongodb/bin:$PATH
//配置完后可以通过echo $PATH查看配置结果。
生效方法：立即生效
有效期限：临时改变，只能在当前的终端窗口中有效，当前窗口关闭后就会恢复原有的path配置
用户局限：仅对当前用户

 

修改方法二：
通过修改.bashrc文件:
vim ~/.bashrc 
//在最后一行添上：
export PATH=/usr/local/mongodb/bin:$PATH
生效方法：（有以下两种）
1、关闭当前终端窗口，重新打开一个新终端窗口就能生效
2、输入“source ~/.bashrc”命令，立即生效
有效期限：永久有效
用户局限：仅对当前用户

 

修改方法三:
通过修改profile文件:
vim /etc/profile
/export PATH //找到设置PATH的行，添加
export PATH=/usr/local/mongodb/bin:$PATH
生效方法：系统重启
有效期限：永久有效
用户局限：对所有用户

 

修改方法四:
通过修改environment文件:
vim /etc/environment
在PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games"中加入“:/usr/local/mongodb/bin”
生效方法：系统重启
有效期限：永久有效
用户局限：对所有用户



遇到只能访问根路由  无法访问其他路由时

	主要是配置 Apache 的 Rewrite：
1、需要在 httpd.conf 中搜索 LoadModule rewrite_module modules/mod_rewrite.so
2、将前面的 # 号去掉，然后在 /extra/httpd-vhosts.conf 中添加
<Directory "配置目录">
  Allowoverride All
</Directory>

3、重启Apache即可解决。

