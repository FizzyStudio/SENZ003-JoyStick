# SENZ003 摇杆模块 

###### 翻译

> `英文`请参考 [`这里`](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/README.md).

> `中文`请参考 [`这里`](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/README_CN.md).

![](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/pic/SENZ003.jpg "SENZ003")  

### 产品介绍

> 采用原装优质金属PS2摇杆电位器制作，具有(X,Y)2轴模拟输出，(Z)1路按钮数字输出。配合Arduino传感器扩展板可以制作遥控器等互动作品。

### 技术参数

* 接口类型：模拟
* 三轴（X，Y，Z（按钮））
* PH2.0接口
* 尺寸：37x25x32mm
* 重量：15克

### 应用
* 游戏手柄

### 引脚说明

![](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/pic/SENZ003_2.png "pin") 

<table>
    <tr with=100%>
        <th bgcolor=bule>引脚 X</th>
    </tr>
    <tr>
        <th>S——模拟输出</th>
        <th>GND——GND</th>
        <th>VCC——VCC</th>
    </tr>
    <tr>
        <th bgcolor=bule>引脚 Y</th>
    </tr>
    <tr>
        <th>S——模拟输出</th>
        <th>GND——GND</th>
        <th>VCC——VCC</th>
    </tr>
    <tr>
        <th bgcolor=bule>引脚 Z</th>
    </tr>
    <tr>
        <th>DATA——数字输出</th>
        <th>VCC——VCC</th>
        <th>GND——VCC</th>
    </tr>
</table>

### 连线图

![](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/pic/SENZ003_3.png "Connection") 

<table>
    <tr>
        <th bgcolor=bule>引脚 X</th>
    </tr>
    <tr>
        <th>S——A1</th>
        <th>GND——GND</th>
        <th>VCC——VCC</th>
    </tr>
    <tr>
        <th bgcolor=bule>引脚 Y</th>
    </tr>
    <tr>
        <th>S——A0</th>
        <th>GND——GND</th>
        <th>VCC——VCC</th>
    </tr>
    <tr>
        <th bgcolor=bule>引脚 Z</th>
    </tr>
    <tr>
        <th>DATA——D3</th>
        <th>VCC——VCC</th>
        <th>GND——VCC</th>
    </tr>
</table>

### 示例代码

> [库安装](https://www.arduino.cc/en/Guide/Libraries#.UxU8mdzF9H0)

    // # 
    // # Editor     : letheascetic from FizzyStudio
    // # Date       : 02.08.2017
     
    // # Product name: Joystick Module
    // # Product ID : SENZ003
    // # Version     : 1.0
     
    // # Description:
    // # Modify the Sample code for the Joystick Module 
     
    // # Connection:
    // #        X-Axis  -> Analog pin 0
    // #        Y-Axis  -> Analog pin 1
    // #        Z-Axis  -> Digital pin 3
    // # 
     
    
    int JoyStick_X = 0; //x
    int JoyStick_Y = 1; //y
    int JoyStick_Z = 3; //key
     
    void setup() 
    {
      pinMode(JoyStick_Z, INPUT); 
      Serial.begin(9600); // 9600 bps
    }
    void loop() 
    {
      int x,y,z;
      x=analogRead(JoyStick_X);
      y=analogRead(JoyStick_Y);
      z=digitalRead(JoyStick_Z);
      Serial.print(x ,DEC);
      Serial.print(",");
      Serial.print(y ,DEC);
      Serial.print(",");
      Serial.println(z ,DEC);
      delay(100);
    }

### 更多
