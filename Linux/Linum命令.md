# cat
1. cat 命令用于连接文件并打印到标准输出设备上。  
2. 参数-n 由 1 开始对所有输出的行数编号。  
##使用
1. 把 textfile1 的文档内容加上行号后输入 textfile2 这个文档里：\
> cat -n textfile1 > textfile2
2. 把 textfile1 和 textfile2 的文档内容加上行号（空白行不加）之后将内容附加到 textfile3 文档里：\
> cat -b textfile1 textfile2 >> textfile3
3. 展示文件内容\
-b ：列出行号，仅针对非空白行做行号显示，空白行不标行号！
-n ：列印出行号，连同空白行也会有行号，与 -b 的选项不同；
-v ：列出一些看不出来的特殊字符
> cat filename.txt

# chmod
1. Linux/Unix 的文件调用权限分为三级 : 文件拥有者、群组、其他。利用 chmod 可以藉以控制文件如何被他人所调用。
2. 语法和参数说明
### 语法
chmod [-cfvR] [--help] [--version] mode file...
### 参数说明
mode : 权限设定字串，格式如下 :\
[ugoa...][[+-=][rwxX]...][,...]

    u 表示该文件的拥有者，g 表示与该文件的拥有者属于同一个群体(group)者，o 表示其他以外的人，a 表示这三者皆是。
    + 表示增加权限、- 表示取消权限、= 表示唯一设定权限。
    r 表示可读取，w 表示可写入，x 表示可执行，X 表示只有当该文件是个子目录或者该文件已经被设定过为可执行。
    -R : 对目前目录下的所有文件与子目录进行相同的权限变更(即以递回的方式逐个变更)

## 使用
1. 将文件 file1.txt 设为所有人皆可读取 :
> chmod ugo+r file.txt
2. 将文件 file1.txt 设为所有人皆可读取 :
> chmod a+r file.txt
3. 将文件 file1.txt 与 file2.txt 设为该文件拥有者，与其所属同一个群体者可写入，但其他以外的人则不可写入 :
> chmod ug+w,o-w file.txt file2.txt
4. 将 ex1.py 设定为只有该文件拥有者可以执行 :
> chmod u+x ex1.py
5. 将目前目录下的所有文件与子目录皆设为任何人可读取 :
> chmod -R a+r *

# 处理目录的常用命令
---
# ls
1. 列出目录。选项与参数：

    -a ：全部的文件，连同隐藏文件( 开头为 . 的文件) 一起列出来(常用)
    -d ：仅列出目录本身，而不是列出目录内的文件数据(常用)
    -l ：长数据串列出，包含文件的属性与权限等等数据；(常用)

# cd
1. 变换工作目录的命令。演示通过相对路径和绝对路径切换工作目录。
> #使用 mkdir 命令创建 runoob 目录
[root@www ~]# mkdir runoob

>#使用绝对路径切换到 runoob 目录
[root@www ~]# cd /root/runoob/

>#使用相对路径切换到 runoob 目录
[root@www ~]# cd ./runoob/

# pwd
1. 显示当前路径.Print Working Directory

# mkdir
1. 创建新的目录。
> mkdir -p test1/test2/test3/test4
2. 创建目录的同时赋予新的属性。
> mkdir -m 711 test2

# rmdir
1. 删除空的目录
> rmdir -p test1/test2/test3/test4

# cp
1. 复制文件或目录.由绝对路径到相对路径。
2.语法
>[root@www ~]# cp [-adfilprsu] 来源档(source) 目标档(destination)\
[root@www ~]# cp [options] source1 source2 source3 .... directory
3. 参数\
-i：若目标档(destination)已经存在时，在覆盖时会先询问动作的进行(常用)\
-p：连同文件的属性一起复制过去，而非使用默认属性(备份常用)；\
-r：递归持续复制，用於目录的复制行为；(常用)
4. 用 root 身份，将 root 目录下的 .bashrc 复制到 /tmp 下，并命名为 bashrc:
> cp -i ~/.bashrc /tmp/bashrc

# rm
1. 移除文件或目录
2. 参数与选项：\
-f ：就是 force 的意思，忽略不存在的文件，不会出现警告信息；\
-i ：互动模式，在删除前会询问使用者是否动作\
-r ：递归删除啊！最常用在目录的删除了！这是非常危险的选项！！！
3.示例：
> rm -i bashrc

# mv
1. 移动文件与目录，或修改名称\
[root@www ~]# mv [-fiu] source destination
[root@www ~]# mv [options] source1 source2 source3 .... directory
2. 参数：\
     -f ：force 强制的意思，如果目标文件已经存在，不会询问而直接覆盖；\
    -i ：若目标文件 (destination) 已经存在时，就会询问是否覆盖！\
    -u ：若目标文件已经存在，且 source 比较新，才会升级 (update)
3. 重命名演示：
> mv mvtest mvtest2

# 磁盘管理
---
# tree
1. 执行tree指令，它会列出指定目录下的所有文件，包括子目录里的文件。
2. 参数说明。\
-a 显示所有文件和目录。
-C 在文件和目录清单加上色彩，便于区分各种类型。
-d 显示目录名称而非内容。
-p 列出权限标示。
-L level 限制目录显示层级。





























