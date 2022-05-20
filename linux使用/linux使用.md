# linux的使用

### 常用命令

* which 查看指令执行文件所在的目录

  which node,which vue

* ln -s path name  创建软连接,path文件的绝对路径 name为指令的名称





### 硬链接和软连接

[Linux 硬链接与软链接](https://www.runoob.com/note/29134)

* 硬连接指通过索引节点来进行连接.两个连接指向相同的文件,其中一个删除,文件并不会删除.
* 软连接类似于快捷方式,主从关系.当文件删除时,软连接仍存在只是指向无效的连接.

![image-20220513145300529](/Users/m1pro/Desktop/mine/sj-md/linux使用/linux使用.assets/image-20220513145300529.png)

