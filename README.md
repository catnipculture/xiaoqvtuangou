> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

​

系统有管理员，用户两个角色。

主要的功能有用户信息管理、商品信息管理、商品类型管理、商品订单管理、公告信息管理、公告类型管理

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：SpringBoot + MyBatis + Vue + Bootstrap + jQuery

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)



# 运行截图

## 文档截图

![img](https://img-blog.csdnimg.cn/img_convert/b59dff10602fc7e9cf5954cf8639fa48.png)

![springboot254小区团购管理0](https://img-blog.csdnimg.cn/img_convert/e1170e5ad0e8b6a3d62c0a25babb9a0e.png)

![springboot254小区团购管理1](https://img-blog.csdnimg.cn/img_convert/f15ea840f11cd1d59c62a72c9db87ca3.png)

![springboot254小区团购管理2](https://img-blog.csdnimg.cn/img_convert/4496de1899101da024ddf36e6bd2bbeb.png)

![springboot254小区团购管理3](https://img-blog.csdnimg.cn/img_convert/3e90e8a6ef7857c99f19d0ad7d59c612.png)

![springboot254小区团购管理4](https://img-blog.csdnimg.cn/img_convert/77ffad6957b87a451993a1607347dc2b.png)

![springboot254小区团购管理5](https://img-blog.csdnimg.cn/img_convert/6d7d54b35b54bfdc9be4525fedf94542.png)

![springboot254小区团购管理6](https://img-blog.csdnimg.cn/img_convert/45a8562755e8149bdc5e91d651c2375b.png)

![springboot254小区团购管理7](https://img-blog.csdnimg.cn/img_convert/9ec23b1f42af4c6ba57a182146420875.png)

![springboot254小区团购管理8](https://img-blog.csdnimg.cn/img_convert/79fc4f88729d85e3edcc96a6ea250a83.png)

### 代码

```
        // 获取磁盘占用信息
        File diskPartition = new File("/");
        long totalDiskSpace = diskPartition.getTotalSpace();
        long freeDiskSpace = diskPartition.getFreeSpace();
        long usedDiskSpace = totalDiskSpace - freeDiskSpace;
        double diskUsage = (double) usedDiskSpace / totalDiskSpace * 100;
        BigDecimal totalDiskSpaceBigDecimal = convertLongToBigDecimal(totalDiskSpace);
        BigDecimal usedDiskSpaceBigDecimal = convertLongToBigDecimal(usedDiskSpace);
        dto.setDiskTotalSize(totalDiskSpaceBigDecimal);
        dto.setDiskUsedSize(usedDiskSpaceBigDecimal);
        BigDecimal diskUsagePercent = new BigDecimal(diskUsage);
        diskUsagePercent = diskUsagePercent.setScale(1, RoundingMode.HALF_UP); // 设置小数点后一位，并四舍五
        dto.setDiskUsage(diskUsagePercent);

        log.info("磁盘总大小: {}G", totalDiskSpaceBigDecimal);
        log.info("磁盘已用空间: {}G，内存占用:{}%", usedDiskSpaceBigDecimal, diskUsagePercent);
        return dto;
```
