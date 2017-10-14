---
layout: post
title: Python学习-基础篇01
date: 2017-10-14 
tag: Python
---

### python的语言特性
python  是和java一样的基于虚拟机的语言：先预编译(字节码文件)后解释
python3 中只有整型   没有长整型

### python3 的标准库-学习
```
#Author:zhangmucoder
import getpass#使输入的数字成为密文
import sys
import os
'''print(sys.path)#打印环境变量
print(sys.argv)#打印相对路径
'''
# os.system('df')
#cmd_res = os.system('df')执行命令不保存结果
cmd_res1 = os.popen('df').read()
print(cmd_res1)
# os.makedir('new_dev')

```


### while 和 for循环的学习

```
while  count < 3:
    count+=1
    guess_age = int(input('guess age:'))
    if guess_age == age_of_oldboy:
        print('yes, you got it')
    elif guess_age > age_of_oldboy:
        print('think smaller...')
    else:
        print('think bigger!')
 

 guess_age = int(input('guess age:'))#int类型强转化

for i in range(10):
    print('loop',i)

for i in range(0,10,2):   #range函数：输入从0 ~ 10 的偶数
    print('loop',i)

```
###  string操作的学习
```
#Author:zhangmucoder

import copy

name = input('username:')
password = input('password:')
job = input('job:')
age = input('age:')
salary = input('salary:')

#字符串拼接的三种方式
info = """
--------- info of %s  -------
Name:%s
Password:%s
Job:%s
Age:%s
Salary:%s
"""%(name,name,password,job,age,salary)


info2 = """
--------- info of {name}  -------
Name:{name}
Password:{password}
Job:{job}
Age:{age}
Salary:{salary}
""".format(name=name,password=password,job=job,age=age,salary=salary)

info3 = """
--------- info of {0}  -------
Name:{0}
Password:{1}
Job:{2}
Age:{3}
Salary:{4}
""".format(name,name,password,job,age,salary)
print(info3)

msg = '夜静海涛三万里'
print(msg.encode(encoding='utf-8'))
#转码
print(msg.encode().decode())#解码

--------------------------- string的一些属性 -------------------------------------
name = 'zhangmucoder'
print(name.capitalize())#首字母大写
print(name.count('z'))#有几个
print(name.center(50,'-'))#居中打印
print(name.endswith('er'))#是否以该字符结尾
print(name.expandtabs())#增加空格
print(name.isalnum())#检测是不是数字 返回 false or ture
print(name.isalpha())#检测是不是纯英文 返回 false or ture
print(name.isdecimal())#检测是不是是不是十进制 返回 false or ture
print(name.isdigit())#检测是不是是不是整数 返回 false or ture
print(name.isidentifier())#检测是不是一个合法的标识符  返回 false or ture
print(name.islower())#检测是不是小写  返回 false or ture
print(name.isnumeric())#检测是不是  返回 false or ture
print('+'.join(['1','2','3']))#列表元素拼接成字符串


p = str.maketrans('abcd','1234')
print('alix li'.translate(p))
#自定义加密编码
print('alix li'.split())#按照空格分成一个列表
print('zhangMUOCDER ZHOU'.swapcase())#大小写互换

```
### 列表和元祖的学习
```
#Author:zhangmucoder
import copy
'''names = ['wuyun','dadi','caodi','baiyun']
names.append('wangyangm')#增
names.insert(1,'libi')#插入
names[2] = 'XieDi'#改
names.remove('XieDi')
names.pop()#删掉最后一个 输入下表就可以删除指定元素
# del names[1]  === names.pop()
# names.clear()#清空
# names.reverse() 反转
names2 = [1,2,3]
names.extend(names2)
# del names2  删除变量
print(names)
print(names.count('xieDi'))
# print(names[0])
# print(names[1:3])# 切片
# print(names[-1])#从又开始的最后一个
# print(names[-3:])# 切片
'''

nameArr = ['lantian','baiyun',['zhangmu','coder'],'niuyang','renjia','meijiu']
print(nameArr[0:-1:2]) #跳这打印  (列表的切片)
names3 = nameArr.copy()#浅拷贝
# names3 = copy.deepcopy(nameArr) #深拷贝
print(names3)
print(nameArr)
nameArr[1] = 'china'
nameArr[2][0] = 'ZHANGMU'
print(names3)
print(nameArr)
#浅拷贝   小列表只是一个内存地址 大列表只是存的一个地址
```
元祖只是列表的一个特殊表达 ------ 只读列表
```
#元组就是只读列表
student = ('name','dog','fox')
print(len(student))
print(student[1])

for i in enumerate(student):
    print(i)
    #isdigit  //判断是不是数字

color_str = '打印颜色'
print('language color:\033[31;1m%s\033[0m'%(color_str))
print('backView  color:\033[41;1m%s\033[0m'%('背景颜色'))
```

### 字典的学习
>*  setdefault:如果有key返回原有的value，如果没有重新添加一条
>*  update:合并字典  如果有key更新value  如果没有新增一条

```
#Author:zhangmucoder
#字典 （OC用法一样 ）
info = {
    'stu001':'baiyun',
    'stu002':'heitu',
    'stu003':'shachenbao'
}

info.setdefault('台湾',{'taiwan':'www.baidu.com'})#如果有key返回原有的value，如果没有重新添加一条

b = {
    'stu001':'zhangmucoder',
    1:2,
    3:5
}
info.update(b)#合并字典  如果有key更新value  如果没有新增一条
print(info)
'''print(info['stu001'])

# del  想删除谁就删谁
# del info['stu001']#删除指定元素
info.pop('syu001')
# info.popitem()#随便删除一个
print(info.get('stu004'))
print('stu005' in info)#检查有没有这个元素
'''
```
<br>
转载请注明：[心明无言的博客](https://zhangmucoder.github.io)  


