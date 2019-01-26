Start the SSH daemon so that we can login to the raspberry pi from a laptop over WiFi.

1. In a terminal run the following:
  ```
sudo raspi-config
  ```
  Navigate to "Advanced Options" and select "SSH", "Enable", "OK"

  Back at the main screen, tab to "Finish" and quit.d

2. Install a ssh client for your laptop(s). For Windows: putty.exe from www.putty.org.

3. Join the same WiFi network with your laptop as the raspberry pi is configured to join. 

4. Figure out the IP address the raspberry pi received from the router. For this you may need to log into the router (192.168.0.1 or 10.0.0.1) and find the DHCP client table. If possible, once you figure out which one is the raspberry pi, set its IP address as a "reservation" so that it gets this IP address next time (and you don't have to look it up). Alternatively, there is an iphone app called Fing which can scan all the ip addresses of a subnet 192.168.0.XXX and identify the make and model of the device at the IP address. 

5. In your SSH client, connect to the raspberry pi's IP address, port 22, and use the username pi and password raspberry (defaults). 

