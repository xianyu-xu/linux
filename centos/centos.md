####安装好系统的第一步--检查是否能上网
如果出现Couldn't resolve host
第一、检查你的网络是否可联网
第二、如果你的网络没有问题，那就是配置的问题了

    # vi /etc/resolv.conf

    在末尾添加
    
    nameserver 8.8.8.8 
    nameserver 8.8.4.4 
    serchdomain localdomain
####第二部、更新你的yum
    # yum update
####第三部、汉化（这个可以不要哈）
    # locale //查看语言包

    如果没有，就安装一下
    # yum groupinstall chinese-suppport

    安装好之后，更改配置
    # vim /etc/sysconfig/i18n
    ```
        LANG="en_US.UTF-8"//英文
        LANG="zh_CN.UTF-8"//中文
    ```

    然后重启，如果没有报错  就ok啦