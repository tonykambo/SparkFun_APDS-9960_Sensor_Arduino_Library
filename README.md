# DFRobot and NodeMCU Support

Incorporates changes to support DFRobot's version of the APDS-9960 sensor ([SEN0817](https://www.dfrobot.com/product-1361.html)). DFRobot's sensor has a different orientation compared to the SparkFun device thus the gesture decoding in ```SparkFun_APDS9960::decodeGesture()``` in ```SparkFun_APDS9960.cpp``` was remapped. See DFRobot's [Wiki](https://www.dfrobot.com/wiki/index.php/SEN0187_RGB_and_Gesture_Sensor) for instructions on using their device.

This fork is a merger of Jonathan Ulmer's [modifications](https://github.com/jonn26/SparkFun_APDS-9960_Sensor_Arduino_Library) to the SparkFun [library](https://github.com/sparkfun/SparkFun_APDS-9960_Sensor_Arduino_Library) to support the ESP8266 (though I backed out the change to the LEDBOOST given it worked fine with DFRobot's device with original code) and DFRobot's [version](https://github.com/Arduinolibrary/DFRobot_RGB_and_gesture_sensor/) of the library (only the remapped gesture decoding code in ```SparkFun_APDS9960::decodeGesture()``` to handle the change in orientation). 

Original README from Jonathan Ulmer's [modifications](https://github.com/jonn26/SparkFun_APDS-9960_Sensor_Arduino_Library):

SparkFun APDS9960 RGB and Gesture Sensor Arduino Library -- Modified for esp8266 
=========================================================

Made a few changes to get this to work with esp8266.

The main two are:
* Removing wire.begin() from SparkFun_APDS9960.cpp and moving it into the examples so that the pins it uses can be specified in your sketch

* Changed the LED_BOOST_300 to LED_BOOST_100 in SparkFun_APDS9960.cpp as I couldn't get the gesture sensor to work without changing this

See Sparkfun's original library here https://github.com/sparkfun/SparkFun_APDS-9960_Sensor_Arduino_Library for usage.

