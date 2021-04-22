# -Simulink-
使用matlab2020的树莓派配置部分及对应的镜像系统操控树莓派，利用Simulink进行半实物仿真。
MATALB2020 连接 树莓派教程




一、找到下载好的matlab对树莓派的支持包

![image](https://user-images.githubusercontent.com/62105777/115750643-f8556780-a3ca-11eb-89ba-2759aa6a50dc.png)


 
 
 
 
 
 
 
 
 
 
 
 
 
点击matlab support package 右边的设置符号，页面如下：






![image](https://user-images.githubusercontent.com/62105777/115750811-28046f80-a3cb-11eb-86c4-b0f90b032ffd.png)








 
选择pi 4，只有matlab2020及其以上版本才支持树莓派4B，点击next







![image](https://user-images.githubusercontent.com/62105777/115750903-3ce10300-a3cb-11eb-8fef-9d4fd0aafdef.png)













 
点击第一个配置matlab树莓派镜像，点击next








![image](https://user-images.githubusercontent.com/62105777/115751000-52562d00-a3cb-11eb-839d-faa81bf005be.png)












 
随便点击一个下载，后面是下载地址，然后next









![image](https://user-images.githubusercontent.com/62105777/115751063-626e0c80-a3cb-11eb-8f82-a67e18d5ab2f.png)











 
 
 
 
点击browse浏览到镜像的位置，点击validate，验证镜像是否可用，然后点击next。







![image](https://user-images.githubusercontent.com/62105777/115751142-76197300-a3cb-11eb-9e14-e36e80b0cf03.png)



















 
进入连接方式配置，我们选择第三个通过网线直接连接，点击next



![image](https://user-images.githubusercontent.com/62105777/115751271-9a754f80-a3cb-11eb-9797-c9e82ed4053a.png)



















 
插入SD卡安装matlab固件，然后next，write，


![image](https://user-images.githubusercontent.com/62105777/115751329-ae20b600-a3cb-11eb-8201-b5a2ae49903a.png)













 
连接硬件，按照上图连接树莓派。此时用手机打开热点，连接电脑，树莓派通过网线连入电脑，树莓派要配置好ssh文件和wpa_supplicant文件，里面配置手机热点的名字和热点的密码。（由于校园网连接要登录验证，所以采用手机开热点的方法）。点击next，会出现检测画面。


![image](https://user-images.githubusercontent.com/62105777/115751461-ca245780-a3cb-11eb-9289-232d3069a5ec.png)

















 
检测结束后如上图，点击test，检测连接是否正常。再点击next结束连接配置。在命令行输入如下代码，第一个参数为IP地址，第二个是名字，第三个是密码。
 
然后会显示连接进度


![image](https://user-images.githubusercontent.com/62105777/115751541-dc05fa80-a3cb-11eb-997c-f197aeb7c15d.png)


















 
连接成功，返回树莓派的各项参数。

打开simulink的例程 与树莓派连接：这个例程是对树莓派上的绿灯进行闪烁时间的调节，并实时会送端口波形。
 

![image](https://user-images.githubusercontent.com/62105777/115751618-ef18ca80-a3cb-11eb-8dd8-31109db4efee.png)





















![image](https://user-images.githubusercontent.com/62105777/115751691-00fa6d80-a3cc-11eb-9ab7-70b164003a9c.png)








 


首先设置hardware board，设置为树莓派，然后检测器IP地址是否与上面的一致。




![image](https://user-images.githubusercontent.com/62105777/115751745-0e175c80-a3cc-11eb-9803-ad2aa6ef83cf.png)












![image](https://user-images.githubusercontent.com/62105777/115751798-1b344b80-a3cc-11eb-92ae-58cf84838346.png)










 

 
然后点击monitor按键，烧写代码进入树莓派，可以通过调节![image](https://user-images.githubusercontent.com/62105777/115751861-27b8a400-a3cc-11eb-8b1d-5c8becc626e8.png)
 来控制绿灯闪烁的间隔，通过窗口观察端口波形。

还有一个例程：
通过这个例程可以实现舵机的旋转：
 
如图

![image](https://user-images.githubusercontent.com/62105777/115751919-33a46600-a3cc-11eb-8a4d-940c0b5a1459.png)







左端为一个输入的正弦波，通过中间的选择开关，如果输入幅值大于3，输出为1，即高电平，输入幅值小于3，输出为0，即低电平。将出接到simulink support package里面的舵机模块，这样可以输出不同脉宽的PWM波，实现舵机的旋转功能。
