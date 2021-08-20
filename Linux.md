inst.gpt(gpt分区表)

    BIOS boot   2M          主分区
    /boot       1G  xfs     主分区
    /           10G xfs     LVM
    /home       5G  xfs     LVM
    swap        1G  xfs     LVM

系统安装生成文件/root/anaconda-ks.cfg (重建系统kickstart)
隐藏文件以.开头

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

man
1   用户在shell环境中可以操作的指令或可执行文件
5   配置文件或者是某些文件格式
8   系统管理员可用的管理指令
/[word]   查找

info
```
/usr/share/doc

```shell
who
netstat -a
ps -aux
```

```shell
sync
shutdown
reboot
halt
poweroff
```

##systemd
