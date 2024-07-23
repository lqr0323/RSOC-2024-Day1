# RSOC -2024-Day1
---
## 总结
---
通过第一天的学习，对RT-Thread操作系统有了比较完整的了解，学会了点灯和串口发送数据,在这里也非常的感谢RT-Thread的导师哥哥姐姐们！第一次写Github写的不好，见谅！

## 首先，是一些必要步骤
下载一些软件和配置环境不做赘述  

env操作：scons -j12,scons --dist,scons -c,scons等，具备一些Linux开发指令知识会更好  

---
### 1.点灯  
---
首先，在一个文件夹下右键，打开env，输入 scons --dist,创建 dist 文件夹，再用vscode打开dist文件下的project文件夹
在poject目录下，右键打开env，依次输入scons -j12 , scons -c , scons ，然后在vscode中按下键盘上的F5开始调试  

插上开发板，即可看见开发板上的灯交替亮灭  
附图片：  
![light](https://github.com/lqr0323/RSOC-2024-Day1/blob/main/light.jpg)    
附源码：  
```
int main(void)
{
    rt_pin_mode(GPIO_LED_R, PIN_MODE_OUTPUT);

    while (1)
    {
        rt_pin_write(GPIO_LED_R, PIN_HIGH);
        rt_thread_mdelay(500);
        rt_pin_write(GPIO_LED_R, PIN_LOW);
        rt_thread_mdelay(500);
    }
}
```
---
### 2.串口打印 Hello World    
---
步骤同上，只需要修改main.c里面的代码创建一个文件夹来存放hello.c和hello.h  
附结构目录：  
![structure](https://github.com/lqr0323/RSOC-2024-Day1/blob/main/structure.png)    
串口打印截图：  

附hell.c,hello.h,main.c的源代码   
```
//hello.h
#ifndef HELLO_H
#define HELLO_H

#include <rtthread.h>

void Print_Hello_World(void);

#endif

//hello.c
#include "hello.h"

void Print_Hello_World(void)
{
    rt_kprintf("Hello World\n");
}

//main.c
#include <rtthread.h>
#include "hello.h"

int main(void)
{
    while (1)
    {
        Print_Hello_World();    //调用Hello.c里的函数
        rt_thread_mdelay(1000);
    }

    return 0;
}
```



