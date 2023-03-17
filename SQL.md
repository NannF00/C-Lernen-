# 添加数据库到API

![image](https://user-images.githubusercontent.com/117897416/224339908-96849302-0cb4-4948-bfed-c8360433ebbe.png)

在"Package Manager Console"里输入

    add-migration changedCarts (changedCarts是自己定义的描述) (无空格) 
    
# 更新数据库 

![image](https://user-images.githubusercontent.com/117897416/224340289-924f0a88-b39c-4576-84a9-f02f8040508a.png)

    update-database
    
# 数据库里添加新用户

![image](https://user-images.githubusercontent.com/117897416/224340575-0e748243-d84c-42f5-b794-eaa52ea79e48.png)
![image](https://user-images.githubusercontent.com/117897416/224340627-0ddc2a3b-4f32-4861-99db-19e382109827.png)
![image](https://user-images.githubusercontent.com/117897416/224340668-1ece762f-4224-4cc7-bac3-73a6364d7483.png)
![image](https://user-images.githubusercontent.com/117897416/224340736-53eb9c60-181f-49f4-8f1f-c2f6606bcb66.png)
![image](https://user-images.githubusercontent.com/117897416/224340948-f22ee548-22b2-41da-9e0d-7c34d72c7e24.png)
![image](https://user-images.githubusercontent.com/117897416/224340996-e93f1164-e752-43a1-bb8e-37472a446d60.png)
![image](https://user-images.githubusercontent.com/117897416/224341029-69b3d6cc-754d-4e0c-a4c5-3676323fc216.png)

# 用 postman 测试: 用path获取资源

忘记了

# public sever & local sever

public sever : häring , amazon , alibaba ... 任何设备联网都可以访问

local sever : 作为sever的我的电脑,只有和我处于一个网络下的设备可以通过我的http://domain+path访问.

sever 的 IP 地址在APPsetting文件里记录(c# api 项目)

# pgAdmin 找到正确的 数据库

database 的 名字 ,username, password 都在APPsetting里,同一行

