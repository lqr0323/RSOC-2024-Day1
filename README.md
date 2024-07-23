# RSOC -2024-Day1
---
## 总结
---
通过第一天的学习，对RT-Thread操作系统有了比较完整的了解，学会了点灯和串口发送数据

## 首先，是一些必要步骤
下载一些软件和配置环境不做赘述  

env操作：scons -j12,scons --dist,scons -c,scons等，具备一些Linux开发指令知识会更好

### 1.点灯
首先，在一个文件夹下右键，打开env，输入 scons --dist,创建 dist 文件夹，再用vscode打开dist文件下的project文件夹
在poject目录下，右键打开env，依次输入scons -j12 , scons -c , scons ，然后在vscode中按下键盘上的F5开始调试  

插上开发板，即可看见开发板上的灯交替亮灭  
附图片：  
！ [light](https://github.com/lqr0323/RSOC-2024-Day1/blob/main/light.jpg)

