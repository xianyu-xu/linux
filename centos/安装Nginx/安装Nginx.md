#编译安装

####第一步、下载安装包

    # cd /usr/local/src

    # wget http://nginx.org/download/nginx-1.17.0.tar.gz

####第二部、解压
x-解压 v-显示过程 f-路径

    # tar -jxvf 路径（解压.tar.bz2） 
    # tar -zxvf 路径 （解压.tar.gz）

####第三部、指定位置安装
    
    #cd nginx  //进入解压后的文件

    #./configure --prefix=/usr/local/nginx //安装

    #make && make install  //编译安装

####第四部、启动
    # /usr/local/nginx/sbin/nginx //启动

    # /usr/local/nginx/sbin/nginx -s reload //重启

