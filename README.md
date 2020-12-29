源代码下载链接：[sqlite-autoconf-3340000.tar.gz](https://sqlite.org/2020/sqlite-autoconf-3340000.tar.gz)

学习笔记关键字：**Study Notes:**
## 学习进度
#### 阶段一
1. 快速浏览sqlite3.h
当前行：4541
## 如何调试源代码
1. 下载安装[lldb](https://apt.llvm.org/)
1. 编译安装sqlite3
1. 运行sqlite3.
    * `./sqlite3 test.db`
    * `sqlite>create table users (id primary key, name varchar(255))`
    * `sqlite3>insert into users values(1, 'andrew')`
1. 绑定sqlite3进程,其中111590为上一步sqlite3进程id,此步骤会阻塞sqlite3进程 `(lldb)attach -p 111590`
1. 在lldb里设置断点
    * b resolveSelectStep
1. 重启sqlite3进程.`(lldb)c`
1. 触发断点.`sqlite>select * from users;`
