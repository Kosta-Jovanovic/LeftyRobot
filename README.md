# Lefty Robot short description 
Modular rover mecanum wheel vehicle lefty (Lighthearted Entity For Tunneling Yonder) that can add different modules for different purposes 
## Zimski seminar
Project was made possible in science center Petnica (01.07- 07.07.2023.), Seminar of electronics. 

### First Day (02.06.2023):
<li>3d model of robot core was made</li> 
<li>3d model of mechanum wheels was made</li>  

### Second day (03.06.2023):
<li>3d printing of parts</li>

### Third day (04.07.2023.):
<li>Test application construction started</li>
<li>Fixing problems with mechanum wheels</li>

### Fourth day (05.07.2023.):
<li>Construction of mechanum wheels</li>
<li>Finishing of the test app</li>

<p><li>There is chassy left to print out, but cause of the problem with 3d printers it is currently imposible</li></p>
<p>For the start we wanted robot to be functional only trough app, and when we finish robot core and determine the modules that we will use, we will write code for ml.</p>

<p> We used two libraries, SoftwareSerial and AccelStepper. We use the first library because it enables us to use serial communication on any digital pin, in our case for communication through a Bluetooth module. Meanwhile, the AccelStepper library allows us to control stepper motors. It provides easy speed and direction control, supports acceleration and deceleration of the motor.

Digital pins 40 to 47 were chosen because they are part of the "Port C" group on the Arduino Mega board. These pins are connected to the corresponding pins on the microcontroller, allowing easy use with digital input/output functions. Pins 8 and 9 were selected as the standard pins for serial communication.

Setting a maximum motor speed is used to limit the motor's speed and prevent the robot from moving too fast and losing control. "dataIn" refers to all the data sent by another device, which this code reads and uses to control the robot. When we determine the existing "m" using "dataIn", we define a specific function for each "m". For example, if(m==4), the "moveSidewaysLeft()" function is called, which makes the robot move sideways to the left.

When the variable "m" is equal to 12 or 14, there are a few more conditions for triggering certain functions. The "moveTo()" function sets the position the wheel needs to reach, "setSpeed()" is used to set the wheel speed, and if a wheel hasn't reached the correct position, the "runSpeedToPosition()" function is used to increase the speed and bring it closer to the target position.

The last eight functions actually control the robot's movement in different directions. Each function is determined by a combination of "wheelSpeed", "-wheelSpeed", and "0" to achieve different directions.
</p>
