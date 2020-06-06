# 前言
Shell是用户与Linux操作系统沟通的桥梁，也是一种用C语言编写的程序，同时也是命令解释程序的统称。用户既可以输入命令执行，也可以利用Shell脚本编程，用以完成更加复杂的操作。时至今日，Shell编程仍然起着不可忽视的作用，深入地了解和熟练地掌握Shell编程，对更好地了解和使用Linux有着重要的意义。
Linux中有多种Shell，如ash，bash，ksh等，其中，最常用同时也是默认的是bash。当普通用户成功登录，系统将执行一个Shell程序，它提供了命令行提示符。

# bash
1. 文件命名格式: *.sh
2. 常见使用方法：gedit hello.sh
3. 赋予执行的权限：chmod u+x hello.sh
4. 执行：./hello.sh

## 具体用法
1. 文件开头需要用#! /bin/bash
2. 例1，if的形式是 **if - do - then -else -fi**
```bash
#! /bin/bash
read -p "请输入一个数:" temp
if [ $temp -gt 0 ] #这是比较数字大小的一种形式
then
	echo "您输入的是正数"
else
	echo "您输入的是非正数"
fi
```
**整数比较1**\
-eq 等于,如:if [ "$a" -eq "$b" ]\
-ne 不等于,如:if [ "$a" -ne "$b" ]\
-gt 大于,如:if [ "$a" -gt "$b" ]\
-ge 大于等于,如:if [ "$a" -ge "$b" ]\
-lt 小于,如:if [ "$a" -lt "$b" ]\
-le 小于等于,如:if [ "$a" -le "$b" ]

**整数比较2**\
大于(需要双括号),如:(("$a" > "$b"))\
'>=' 大于等于(需要双括号),如:(("$a" >= "$b"))

**字符串比较**\
= 等于,如:if [ "$a" = "$b" ]\
== 等于,如:if [ "$a" == "$b" ],与=等价\
!= 不等于,如:if [ "$a" != "$b" ]\
大于,在ASCII字母顺序下.如:\
 if [[ "$a" > "$b" ]]\
 if [ "$a" \> "$b" ]\
 注意:在[]结构中">"需要被转义.
 
 3. 例2 测试for循环，for循环的形式是**do - done**形式
 ```bash
 #! /bin/bash
read -p "请输入一个正数：" temp
# 此处的for循环类似python，注意要在seq 后加$temp
for i in $(seq $temp)
do
	echo $i
done
 ```
 
 4. 例3，while测试，while循环的形式是**do - done**
 ```bash
 #! /bin/bash

read -p "请输入您的姓名，输入q推出循环：" name
while [ "$name" != "" ] 
do
	if [ "$name" == "q" ]
	then
		break
	fi
	echo "欢迎您,$name"
	read -p "请输入您的姓名，输入q推出循环：" name
done
 ```
 
 5. 例4，自定义函数示例
 ```bash
 #! /bin/bash

function myfunc()
{
  # 不甚清楚为何表达式如此形式，$1代表函数第一个参数
	return $(($1 + $2))
}
read -p "请输入第1个数：" x
read -p "请输入第2个数：" y
myfunc $x $y
total=$?
echo $total
 ```
 
 6. 例5，利用Shell编程，实现1-10的数字累加求和
 ```bash
 #! /bin/bash
 #等于号两边不能有空格
sum=0
for i in $(seq 10)
do
	# 这是(())表达式
	sum=$(($sum+$i))
done
echo "1到10相加的结果为：$sum"
 ```
 
 7. 例6，打印9*9乘法表
 ```bash
 #! /bin/bash
#打印99乘法表
row=1
while [ $row -le 9 ]
    do
       colume=1
       while [ $colume -le $row ]
          do
            echo -n "$row*$colume=$((row*colume)) "
            colume=$(expr $colume + 1)
          done
       echo
       ((row=$row+1))
done

 ```
 
 
 
 
 
 
 
 
 
