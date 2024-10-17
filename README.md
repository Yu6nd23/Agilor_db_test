# Agilor_db_test
###  1.agilor.go
-----主要是在数据传入数据库之前的拆分操作，以及从数据库查询到数据的拼接数据等一系列操作
###  2.lib_agilor/src/agilor_wrap.c 
-----封装函数：该文件包含了大部分安捷原数据库操作函数的封装。
-----新增功能模块：包含了一些根据需求新添加的功能函数。
-----数据类型转换：由于传入的数据是ucs_pt_t类型（定义见agilor_wrap.h），因此还实现了数据类型转换函数如ucsptToAgilorPt和ucsptToAgilorValue，以便与Agilor数据库兼容。
###  3.lib_agilor/src/test_con.c
-----功能测试代码

3.存储在Agilor数据库的主要字段是创建表时的tag，单点数据，时间戳，其他的全部存在第三方数据库

###  目前主要的一些问
###  数据库操作函数运行时会报Segmentation fault (core dumped)错误，目前测试了三个函数只有删除点位信息测试成功了
###  服务器名称获取失败，删除点位测试成功是我手动设置的传入的服务器名参数，如果通过给定的函数获取到的服务器名称传入删除点位的函数，也会报Segmentation fault (core dumped)错误
