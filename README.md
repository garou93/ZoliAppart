# Zoli Appart

## About

Zoli Appart is Raspberry Pi based home automation / smart home / smart house solution based on common and cheap components, works realiably and I think is very convenient to use.

### Main goal for this home automation system was to create something that:
- would work inside of local network and be accessible from any device whether it is computer, phone or tablet for convenient use.
- not to be dependent in any way on anything outside of local network – there are no connections to cloud or some 3rd party services. It is all „inside” of local and independent from outside world. Internet is not needed here – just internal network will suffice.
- most important initial feature of this system was delayed auto disable. Devices that you configure into the system do not have to have that feature enabled but it definately turns out very practical in everyday usage – especially for lamp devices.

### What it currently provides:
- web interface which allows to operate defined devices to anyone from your home network
- it allows control over radio operated devices/power switches
- it allows control over web operated devices/power switches
- provides way to define scheduled working periods for devices by simply clicking in UI
- allows to define auto disable option with delay times after which devices would be turned off (energy saving for forgetting and salvation for lazy ones ;-))
- allows to define PIR sensor(s) connected to Raspberry pi and basing on their signal can operate defined devices and/or trigger alarm/sen alarm mails
- can be easily integrated with Google Voice kit to use voice commands. Example script in one of my repositories.

### How it looks - DEMO Time!
- Work in progress

## Installation & Usage

- Rasberry Pi Raspbian installation and setup
* Installation
    1. Download Noobs image from https://www.raspberrypi.org/downloads/noobs/
    2. Format SD card according to instructions from raspberry pi site.
    3. Copy extracted system files directly to SD card
    4. Run Raspberry Pi and let it install system
    5. after instllation run to have latest version of your system:
        1. sudo apt-get update
        2. sudo apt-get upgrade
        3. sudo apt-get dist-upgrade
* Setup Machine:
    - sudo nano /etc/hosts
    Leave all of the entries alone except for the very last entry labeled 127.0.1.1 with the hostname
    “raspberrypi“. This is the only line you want to edit. Replace “raspberrypi” with whatever
    hostname you desire.
    1. sudo nano /etc/hostname
    2. sudo reboot
* Setup password:
    Sudo raspi-config
* Setup wifi:
    sudo nano /etc/network/interfaces
    sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
* Setup Static IP: 
    Sudo nano /etc/dhcpcd.conf
* Enable FTP:
    1. sudo raspi-config
    2. sudo apt-get install proftpd
        1. choose standalone
        2. [optional config changes] sudo nano /etc/proftpd/proftpd.conf3. sudo service proftpd restart    
* Enable VNC:
    sudo raspi-config
* Install and activate smbus and i2c
    1. sudo apt-get install python-smbus
    2. sudo raspi-config            
* Install and configure Apache and PHP
    1. sudo apt-get install apache2 -y
    2. sudo apt-get install php5 libapache2-mod-php5 -y
    3. sudo apt-get install php5-curl
    4. optional if you want to change apache server root directory
        1. sudo nano /etc/apache2/sites-enabled/000-default.conf
    5. sudo /etc/init.d/apache2 reload

If you left default apache root path which is /var/www/html use below command to add pi user
rights to this ridectory so you will be able to copy data there
1. sudo chown -R pi /var/www/html
We also give apache proper rights so it can run shell commands which will be needed when running
Zoli Appart scripts


- Zoli Appart files deployment
    Deploy files to Raspberry pi:
    Modify settings file:
    Apply permissions to folders:
    Compile signal sending files:
    Setup startup scripts:

- Radio Controlled Switches setup
    Radio Controlled Switches setup:
    Reading Radio controlled power switch signal using RFSniffer

- Web Controller Switches Setup:

- configuration:
    Settings.json file setup
(Documentation in progress)

## What you need to run it

- to run the system you just need Raspberry Pi with Apache + PHP configured, Python is also used but it is by default included in Raspbian. Configuration is described in instructions above.
- to control radio controller power switches you would need such switches and RF radio transmitter like **XY-FST**
- to control web controlled power switches you would need such switches - **SONOFF** devices are ideal for this with custom scripts uploaded. I use such scripts but have not yet uploaded them here will probably do so in the feature with some explanation hot to flash these switches.
- to use pir sensor you would need pir sensor for Raspberry PI like **HC SR501**

## Notes
- if you have questions/suggestions you can contact me through github account mail.

## Example Screens

Work in progress

## Tests

Work in progress

