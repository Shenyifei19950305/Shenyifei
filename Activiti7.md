# Activiti7

工作实现原理

![image-20200718120227349](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718120227349.png)

![image-20200718120821104](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718120821104.png)

![image-20200718121441519](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718121441519.png)![image-20200718121519512](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718121519512.png)

![image-20200718123134903](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718123134903.png)

![、](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718164002942.png)

环境搭建

![image-20200718164202880](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718164202880.png)

![image-20200718164404751](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718164404751.png)

![image-20200718164441123](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718164441123.png)

安装

![image-20200718172513956](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718172513956.png)

![image-20200718165151200](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718165151200.png)

做完bpm图，放到桌面打开，是一个xml文件

![image-20200718165216098](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718165216098.png)

![image-20200718173320221](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718173320221.png)

这边采用的是mysql

![image-20200718174641401](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718174641401.png)

![image-20200718174842108](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200718174842108.png)

具体代码省略，接下来就是在resource里面导入log4j的文件，这边导师已经提前给我们了

![image-20200719113559685](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719113559685.png)

然后同样在resource里面还需要导入activiti.conf.xml文件

把这些内容导进去，里面有dbcp数据源，也有activiti单独运行的配置

![image-20200719113901370](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719113901370.png)

接下来编写我们的测试代码，进行测试运行下

![image-20200719114905844](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719114905844.png)

测试成功如下

![image-20200719114307046](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719114307046.png)

查看数据库，会自动生成表字段

![image-20200719114448272](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719114448272.png)



目前为止已完成的流程

![image-20200719122747515](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719122747515.png)

![image-20200719122947045](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719122947045.png)

processEngine也定义了很多方法

![image-20200719154527351](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719154527351.png)

假如你现在有个业务，你想list数据表里面的history数据，如果是正常代码实现就是domain-dao-service list出来。但是activiti不是，是直接通过activiti直接操作 getHistoryService 直接进行增删改查

Spring整合activiti 有直接的配置文档

![image-20200719155258277](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719155258277.png)

![image-20200719155410582](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719155410582.png)

关于processEngine的创建，前面说了一种，现在说最简单的第二种创建25种表达方式，但是，会有几个命名条件必须遵守，否则，是创建不成功的![image-20200719160007639](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719160007639.png)

![image-20200719160802535](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719160802535.png)



上面具体流程可以参考资料，这边就进入新章节了

## Activiti入门体验

现在开始模拟一个请假的流程

先做bpm

![image-20200719162044391](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719162044391.png)



但是bpmn可能会有乱码问题，如何解决乱码问题

idea里面打开这个文件，

![image-20200719164254503](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719164254503.png)

![image-20200719164323402](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719164323402.png)

修改最后一段

接下来就是部署流程定义

![image-20200719214446513](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719214446513.png)

![image-20200719215458452](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719215458452.png)

流程定义的部署

![image-20200719220429372](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719220429372.png)

记录key，然后进行部署

![image-20200719220905125](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719220905125.png)

![image-20200719221102581](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200719221102581.png)