源代码结构

```bash
➜ tree leveldb -L 1 -d 
leveldb     # LevelDB主要实现，包括DB结构体及其方法
├── cache       # 实现缓存算法，存储频繁访问的数据块
├── comparer    # 提供键排序机制，确保数据有序
├── errors      # 定义通用的错误类型
├── filter      # 实现概率数据结构，布隆过滤器，加速查找
├── iterator    # 处理数据库内容的遍历，支持前向和后向迭代
├── journal     # 管理写前日志WAL,确保数据持久性
├── memdb       # 实现内存数据库(memtable),存储最近的写入
├── opt         # 定义数据库的配置选项，如memtable大小和压缩策略
├── storage     # 提供文件系统操作的抽象，处理SSTable和WAL文件的读写
├── table       # 管理排序字符串表(SSTable),用于持久化存储
├── testutil    # 测试工具包
└── util        # 整个库使用的实时工具函数

13 directories
```

