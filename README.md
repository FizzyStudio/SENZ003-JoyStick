# SENZ003 JoyStick Module

###### Translation

> For `English`, please click [`here.`](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/README.md)

> For `Chinese`, please click [`here.`](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/README_CN.md)

![](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/pic/SENZ003.JPG "SENZ003") 

### Introduction

> Lots of robot projects need joystick. This module provides a affordable solution to that. 
Simply connect to two analog inputs, the robot is at your commands with X,Y control. 
It also has a switch that is connected to a digital pin. This joystick module can be easily connect to Arduino by IO Expansion Shield For Arduino with supplied cables.

### Specification

* Supply Voltage: 3.3V to 5V
* Interface: Analog x2,Digital x1
* PH2.0 Interface
* Size:35x39mm
* Weight:15g

### PinOut

![](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/pic/SENZ003_2.png "pin")  

<table>
    <tr with=100%>
        <th bgcolor=bule>Pin X</th>
    </tr>
    <tr>
        <th>S——Analog OUT</th>
        <th>GND——GND</th>
        <th>VCC——VCC</th>
    </tr>
    <tr>
        <th bgcolor=bule>Pin Y</th>
    </tr>
    <tr>
        <th>S——Analog OUT</th>
        <th>GND——GND</th>
        <th>VCC——VCC</th>
    </tr>
    <tr>
        <th bgcolor=bule>Pin Z</th>
    </tr>
    <tr>
        <th>DATA——Digital OUT</th>
        <th>VCC——VCC</th>
        <th>GND——VCC</th>
    </tr>
</table>

### Tutorial

#### Connection Diagram

![](https://github.com/FizzyStudio/SENZ003-JoyStick/blob/master/pic/SENZ003_3.png "Connection") 

<table>
    <tr>
        <th width=100%, bgcolor=bule>Pin X</th>
    </tr>
    <tr>
        <th>S——A1</th>
        <th>GND——GND</th>
        <th>VCC——VCC</th>
    </tr>
    <tr>
        <th width=100%, bgcolor=bule>Pin Y</th>
    </tr>
    <tr>
        <th>S——A0</th>
        <th>GND——GND</th>
        <th>VCC——VCC</th>
    </tr>
    <tr>
        <th width=100%, bgcolor=bule>Pin Z</th>
    </tr>
    <tr>
        <th>DATA——D3</th>
        <th>VCC——VCC</th>
        <th>GND——VCC</th>
    </tr>
</table>

#### Sample Code

> [Libary installation](https://www.arduino.cc/en/Guide/Libraries#.UxU8mdzF9H0)

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

### More
