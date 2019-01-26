A number of devices and daemons need to be set up to work with the GPS and magnetometer

1. I2C communication bus. In a terminal run the following:
  ```
    sudo raspi-config
  ```
  Navigate to "Advanced Options" and select I2C, select "Enable", "OK", "Yes", "OK". 

  Back at the main screen, tab to "Finish" and quit.

1. GPS daemon. In a terminal run the following:
  ```
   sudo dpkg-reconfigure gpsd
  ```
  Select "Yes", "Yes", type "/dev/ttyAMA0", tab "OK", tab "OK", tab "OK" 
