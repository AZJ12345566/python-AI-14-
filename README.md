# python-AI-14-
python+AI笔记(14)
# 一阶-六章-字典的定义
#字典是通过key找到value

#定义字典
my_dict={"王力红":99,"周杰轮"：88,"林俊节":77}
#定义空字典
my_dict2={}  #这就是空集合为什么定义为set()
my_dict3=dict()
print(f"字典1的内容是:{my_dict1},类型:{type(my_dict1)}")
print(f"字典1的内容是:{my_dict2},类型:{type(my_dict2)}")
print(f"字典1的内容是:{my_dict3},类型:{type(my_dict3)}")

#定义重复key的字典
my_dict={"王力红":99,"王力红"：88,"林俊节":77}。#此行代码会警告，输出出来，只会出现后一个重复对象，前面一个对象自动删除

#从字典中基于key获取value
my_dict1={"王力红":99,"周杰轮"：88,"林俊节":77}
score=my_dict1["王力红"]
print(score)  #输出99

#注：字典中的key和value类型是不受限制的，所以，字典是可以嵌套的

#定义嵌套字典
stu_score_dict={
    "小明":{"语文:77,"数学":66,"英语":33},"小红":{"语文":88,"数学":86,"英语":55},"小强":{"语文":99,"数学":96,"英语":66}
}
print(stu_score_dict)

#从嵌套的字典中获取数据
#看一下小红的语文信息
score=stu_score_dict["小红"]["语文"]
printt(score)

# 一阶-六章-字典的常用操作
#更新以及新增元素
#语法:字典[key]=value  如果元素不存在则是新增元素，如果元素存在，则是更新元素

my_dict={"小红":99,"小蓝":88,"小刚":77}
#新增元素
my_dict["小强"]=66
print(my_dict)  #小强已经被添加在末尾

#更新元素
my_dict["小红"]=33
print(my_dict)  #小红已经存在在字典当中，自动更新元素

#删除元素
score=my_dict.pop("小红")  #pop用于key而不是value
print(my_dict,score)

#清空元素
my_dict.clear()
print(my_dict)  #字典已经被清空了

#获取全部key的相关操作
my_dict={"小红":99,"小蓝":88,"小刚":77}
keys=my_dict.keys()
print(keys)  #将所有的key输出

#遍历字典
#依次取到key可以用来做字典的遍历
for key in keys:
    print(key,my_dict[key])
#方式2:直接对字典进行for循环，每一次循环都是直接得到key
for key in my_dict:
    print(key,my_dict[key])
#字典不支持下标索引，正常情况下不能使用while循环

#统计字典的元素数量
num=len(my_dict)
print(num)

# 一阶-六章-字典课后练习讲解
info_dict={
    "王力红":{
        "部门":"科技部"，
        "工资":3000,
        "级别":1
        },
    "周杰轮":{
        "部门":"市场部"，
        "工资":5000,
        "级别":2
    },
    "林俊节":{
        "部门":"市场部"，
        "工资":7000,
        "级别":3
    },
    "张学油":{
        "部门":"科技部"，
        "工资":4000,
        "级别":1
    },
    "刘德滑":{
        "部门":"市场部"，
        "工资":6000,
        "级别":2
    }
}

#for循环遍历字典
for name in info_dict:
    if info_dict[name]["级别"]==1:
        employee_info_dict=info_dict[name]
        employee_info_dict["级别]=2
        employee_info_dict["工资"]=employee_info_dict["工资"]+1000
        #将员工信息更新回info_doct
        info_dict[name]=employee_info_dict
print(info_dict)

# 一阶-六章-5类数据容器的总结对比
#从是否支持下标索引分类
#支持:列表、元素、字符串 - 序列类型
#不支持:集合、字典 - 非序列类型

#是否支持重复元素:
#支持：列表、元组、字符串 - 序列类型
#不支持:集合、字典 - 非序列类型

#是否支持修改
#支持:列表、集合、字典
#不支持:元组、字符串

#支持下标索引的数据容器数据就有序

# 一阶-六章-数据容器的通用操作
#len()、max()、min()来统计元素的数量
#list()、str()、tuple()、set()来进行容器的通用转换功能

#通用排序功能
sorted(容器,[reverse=True])

print(sorted(my_list),[reverse=True])  #将五大类的数据容器都转换为有序的序列
#注:排序的结果统统变为列表对象
