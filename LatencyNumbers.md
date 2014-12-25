用数据来衡量数据架构
============
根据一些paper,及自己的经验 总结了一些算机系统操作响应时间 汇总如下:
___

ms 毫秒=0.001秒 

us 微秒=0.000001秒

ns 纳秒=0.000000001秒



Hardware

task| time
--- |-----
机械硬盘顺序读取1MB| 20~25 ms
Disk seek(机械硬盘一次寻址定位) | 8~10 ms
SSD顺序读取1MB| 1ms
SSD随机读取4K | 0.15 ms 
L1 Cache Reference| 1ns
L2 Cache Reference | 7ns
Main memory reference |100ns
内存中顺序读取1MB数据| 0.25 ms



Software

task| time
----|:----
Redis读取一个数据| 0.5 ms
RDBMS使用索引查询一条记录| 15 ms
Java native invoke method| 5 微秒
Mutex lock/unlock | 25ns
互斥锁定/解锁| 100ns
Zip压缩 1K bytes | 3000 ns



Network

task| time
----|----
打开一个网站 | 3s内算正常
Round trip within data center| 0.5 ms
网络传输1K数据(1Gbps network )| 10000 ns
网络传输1MB数据(1Gbps network )| 10ms



Mobile

运营商| 网络 | 实机速度| 理论速度
----|----|---------|---------
移动   |  HSDPA：|  60KB/s    |
移动   |  EDGE:    | 20KB/s     |   48KB/s    
联通   |  HSDPA：|  500KB/s  | 
联通   |  GSM:      | 6KB/s       |
电信   |  3G：      | 60KB/s     |



汉字字符(gbk): 2byte 
汉字字符(utf8): 3byte
字母: 1byte





