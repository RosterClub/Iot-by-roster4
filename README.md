# Iot-by-roster4
Iot by roster4
GPS module with Raspberry Pi 
CONNECT YOUR CIRCUIT:
1.Connect the VCC pin of GPS Module to 3.3V pin of USB to TTL converter.
2.Connect the GND pin of GPS Module to GND pin of USB to TTL converter.
3.Connect the Tx pin of GPS Module to Rx pin of USB to TTL converter.
4.Connect the Rx pin of GPS Module to Tx pin of USB to TTL converter.
5.Lastly, connect the USB to TTL converter to USB port of Raspberry Pi.
Now type the following commands to get update and upgrade the raspberry and install packages
->ls /dev/ttyUSB
->sudo cat /dev/ttyUSB

To install gpsd, make sure your pi has an internet connection and run the following command from the console

->sudo apt-get update
->sudo apt-get install gpsd gpsd-clients python-gps
->sudo systemctl stop gpsd.socket
->sudo systemctl disable gpsd.socket
->sudo systemctl enable gpsd.socket
->sudo systemctl start gpsd.socket

After installing and disabling the gpsd systemd service as mentioned above you are ready to start using gpsd yourself.
Start gpsd and direct it to use USB simply entering the command 

->sudo gpsd /dev/ttyUSB0 –F /var/run/gpsd.sock


which willpoint the gps daemon to our gps device on the /dev/ttyAMA0 console
Try running gpsmon to get a live streaming update of GPS data! Or cgps which 
gives a less detailed but still quite nice output
->cgps –s
You can abort gpsd by the following command
->sudo killall gpsd

Download or copy the code from the following link: 
http://www.electronicwings.com/raspberry-pi/gps-module-interfacing-with-raspberry-pi

