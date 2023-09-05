# C_KVstore

#### 文件介绍
1. NtyCo: 协程的实现，kvstore是基于协程实现
2. kvstore.c: 实现了网络基础库与kv应用协议解析
3. rbtree.c: 实现了rbtree 并封装了符合kvstore的api
4. hash.c: 实现了hash 并封装了符合hash的api
5. testcase.c: 测试用例


#### 代码编译
```
$ cd C_KVvstore/NtyCo
$ make  # 先编译NtyCo,生成libntyco.a

$ cd ../ # 进入kvstore的根目录
再编译kvstore.c 
$ gcc -o kvstore kvstore.c -I ./NtyCo/core/ -L ./NtyCo/ -lntyco -lpthread -ldl 
```

#### 代码编译（20230807以后的版本）
```
$ cd C_KVvstore/
$ make

```

#### 执行
```
# kvstore服务启动
$ ./kvstore # 监听端口8000

打开另一个ssh终端
# 客户端连接
$ telnet xx.xx.xx.xx 8000 #xx.xx.xx.xx为kvstore服务的ip地址

```
