# Readme
A note about different types of databases.

### 不同类型的数据库

##### 严格要求存储一致性的数据库

存储一致性是指数据在内存和外存之间的一致程度。

存储一致性关于Sync Rate的函数的特点是：Sync Rate越小，存储一致性越小，Sync Rate越大，存储一致性越大。

许多场景对存储一致性有严格的要求，必须把Sync Rate设置成某个很大的值，但是在Sync Rate的值很大的情况下，随着数据量的增大，Sync会占据越来越多的CPU周期，磁盘IO也会逐渐满载，响应及时性会逐渐降低直至丧失。

##### 严格要求响应及时性的数据库
严格要求响应及时性的数据库不严格要求存储一致性，可以自由调节Sync Rate的值，有时候甚至可以把Sync Rate的值设置成0。

由于没有Sync Rate的束缚，所以不会出现CPU满载和磁盘IO满载的情况，但是会出现网络IO满载的情况。

##### 文档数据库

##### 文件数据库

##### 要求对齐的数据库
有些数据库通过要求对齐来提高查找速度，所以要求对齐其实并不是一种用户期待的特性，而是一种约束。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
