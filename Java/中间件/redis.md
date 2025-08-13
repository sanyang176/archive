项目经验：调研Satoken的redis插件能否改用hash存储，因为hash存储调用的put需要3个字段，get需要两个字段，而satokendao里面没有对应方法
redis 有5种数据结构
string
hash
list
set
zset（有序集合）
