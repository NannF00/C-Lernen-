# Bug 1

建立服务器时出错 -> startup配置文件有问题 ->
![image](https://user-images.githubusercontent.com/117897416/222759918-e82907ce-6c70-4c5d-8f73-da558f2ce30f.png)
 -> debug : repository 的映射忘记加了 
![image](https://user-images.githubusercontent.com/117897416/222760174-7150f68b-3d19-404f-86f8-75718ce52807.png)

# Bug 2

cart 的 Get 功能一直显示 customer = null.

解决方法:

1. 手动添加函数customer.FindByCustomerId(),

2. 用customerId寻找到customer资源,手动赋进去.(在CartController里)

主要改动,不是全部
![image](https://user-images.githubusercontent.com/117897416/228819435-709709ca-0f51-492f-9ea0-5f046320879c.png)
![image](https://user-images.githubusercontent.com/117897416/228819178-ed4792f8-d716-44e9-83b8-9eed46c39041.png)
![image](https://user-images.githubusercontent.com/117897416/228819738-00aaa291-f3db-412c-bd45-3c6fa99f2b6e.png)


