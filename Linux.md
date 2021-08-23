inst.gpt(gpt分区表)

    BIOS boot   2M          主分区
    /boot       1G  xfs     主分区
    /           10G xfs     LVM
    /home       5G  xfs     LVM
    swap        1G  xfs     LVM

系统安装生成文件/root/anaconda-ks.cfg (重建系统kickstart)
隐藏文件以.开头

    /root       与开机系统有关
    /usr        与软件安装执行有关
    /var        与系统运作过程有关

修改密码
1. Linux16 行尾 init=/bin/sh
2. Ctrl+X进入单用户模式
3. 
    mount -o remount,rw /
    passwd
    修改
    touch /.autorelabel
    exec /sbin/init

文本界面启动X窗口界面
```shell
startx
```

```shell
exit
ls
date
cal
bc
```

```shell
--help

man         #/usr/share/man          /etc/man_db.conf
    #1   用户在shell环境中可以操作的指令或可执行文件
    #5   配置文件或者是某些文件格式
    #8   系统管理员可用的管理指令

    ?[word]     #向上查找
    /[word]     #向下查找
    n           #下一个
    N           #上一个
    q           #退出

    -f          #查询字符命令                = whatis
    -k          #包含查询字符的命令          = apropos
mandb           # = makewhatis

info        #/usr/share/info
    b   #begin page
    e   #end page
    p   #prev node
    n   #next node
    u   #upper node
    s(/)


/usr/share/doc  #说明文档
```

```shell
who
netstat -a      #网络联机状态
ps -aux
```

```shell
sync            #将数据同步写入硬盘
shutdown
    -k
    -r  #reboot
    -h  #time
    -c  #cancel
reboot
halt
poweroff
```

    /etc/passwd     root密码
    /etc/shadow     个人密码
    /etc/group      组名

文件类型 d:目录 -:文件 l:link b:接口设备 c:串行端口 s:资料接口文件 p:数据输送文件
```shell
chgrp
chown
chmod

mkdir
touch
```

##systemd
