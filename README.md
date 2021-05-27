# RaspberryPiSetup

1) First we are going to download the Raspbian Lite image from the official raspberry pi website - https://www.raspberrypi.org/software/operating-systems/
Note : Here I describe installation of Lite OS as it has the lowest size. You can follow upgrading to Desktop version here https://www.raspberrypi.org/forums/viewtopic.php?t=133691

2) Download and install Etcher - To flash the image to your SD card, we will use the program called Etcher, which is available for Mac, Windows and Linux

3) If you want to format SD card before etching, use SD Card formatter App available for Mac

4) Plug your SD card into your computer (using a microSD USB reader if necessary and run Etcher.

5) Etcher will walk you through selecting the OS image file, selecting your SD card reader, and then flashing it.

6) To activate the SSH server in order to connect to your Raspberry Pi remotely you should create an empty file called "ssh" in the root folder of your SD card. On mac you can use the following command:
   
   ```touch /Volumes/boot/ssh```
   
7) Only If you are using WiFi instead of LAN cable for your Raspberry Pi you should create one more file called “wpa_supplicant.conf” in the root folder of your SD card. Paste the below lines inside it and don't forget to change the "NETWORK-NAME", "NETWORK-PASSWORD" and the ISO 3166 alpha-2 country code (get the code from Wikipedia - https://en.wikipedia.org/wiki/List_of... ) with yours:
  
  ```
  country=US
  ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
  update_config=1

  network={
       ssid="NETWORK-NAME"
       psk="NETWORK-PASSWORD"
  }
  ```
  
  NOTE : This step needs to be everytime we change the router as the file ssh and wpa_supplicant.conf gets auto deleted after we connect to wifi first time.
  
8) Insert the SD card in your Raspberry Pi and power it up

9)  To connect to it use the following command from Mac OS or Linux (For Windows search & download - Putty SSH client): 
    
    ```ssh pi@raspberrypi.local ```
    
    Deafult password raspberry
    
10) To update the Raspberry type the following:
    
    ```sudo apt-get update -y```
    
    ```sudo apt-get upgrade -y```
    
11) Definitely change the default password (which is raspberry) by typing the following command: 
    
    ```passwd```
    
12) Inorder to know the IP address, type 
    
    ```hostname```
   
