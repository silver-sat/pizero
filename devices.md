A number of devices, permissions, and daemons need to be set up to work with the GPS and magnetometer

1. I2C communication bus. In a terminal run the following:
  ```
    sudo raspi-config
  ```
  Navigate to "Advanced Options" and select I2C, select "Enable", "OK", "Yes", "OK". 

  Back at the main screen, tab to "Finish" and quit.
  
2. I2C permissions. In a terminal run the following:
  ```
sudo bash <<EOF
echo 'SUBSYSTEM=="i2c-dev", GROUP="i2cuser", MODE="0660"' > /etc/udev/rules.d/50-i2c.rules
EOF
sudo groupadd i2cuser
sudo adduser pi i2cuser
  ```

3. GPS daemon. In a terminal run the following:
  ```
   sudo dpkg-reconfigure gpsd
  ```
  Select "Yes", "Yes", type "/dev/ttyAMA0", tab "OK", tab "OK", tab "OK" 
