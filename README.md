[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/rtPGwteW)
# First_Task
First_Task for C

如下图所示为流水灯控制原理图，请使用C语言编写逻辑代码，实现从左到右的流水灯，间隔时间为500ms。

![water_led](image.png)

示例代码如下：请在 task.c 中编写你的代码。


```
void delay_ms(unsigned int x)  // 延时函数
{
    unsigned int i,j;
    if(x==1000)
    {
        for(i=0;i<19601;i++)//延时1s
        {
            for(j=5;j>0;j--);
        }
    }
    else while(x--)for(j=115;j>0;j--);
}

// tips: 原理图当中led为低电平点亮，比如点亮LED2,代码为： P0 = 0xFE (1111 1110)


int main(void)
{
   // 编写你的代码
include <reg51.h>  

#define LED_PORT P0  
#define DELAY_MS 500 

void delay_ms(unsigned int ms); 

void main(void) {
    unsigned char led_pattern = 0x01; 

    while (1) { 
        LED_PORT = ~led_pattern; 
        delay_ms(DELAY_MS); 
        led_pattern <<= 1; 
        if (led_pattern == 0x00) {
            led_pattern = 0x01;
        }
    }
}
void delay_ms(unsigned int ms) {
    unsigned int i, j;
    for (i = ms; i > 0; i--) {
        for (j = 114; j > 0; j--); 
｝

    
    

 

    return 0;
}
```

