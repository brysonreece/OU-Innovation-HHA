##Hacking Home Automation - a DIY Approach to Your Very Own Smart Home
Taught at OU's Innovation @ The Edge

---
![Result Flowchart](http://i.imgur.com/Gk2KMJq.png)

##Getting Started
To get started building our very own Smart Home, we need to gather the following hardware:
* Amazon Echo ([Amazon](http://www.amazon.com/Amazon-SK705DI-Echo/dp/B00X4WHP5E/))
* Raspberry Pi 2 ([Element14](http://www.newark.com/raspberry-pi/raspberrypi-2-modb-1gb/sbc-raspberry-pi-2-model-b-1gb/dp/38Y6467), [Adafruit](https://www.adafruit.com/products/2358))
* 8gb MicroSD Card (Class 10) ([Amazon](http://www.amazon.com/SanDisk-MicroSDHC-Standard-Packaging-SDSDQUAN-008G-G4A/dp/B00M55C0VU/), [Adafruit](https://www.adafruit.com/products/2692))
* HDMI Cable ([Amazon](http://www.amazon.com/AmazonBasics-High-Speed-HDMI-Cable-Supports/dp/B00870ZHCQ/), [Adafruit](https://www.adafruit.com/products/608))
* 5v 2A Micro-USB power supply ([Amazon](http://www.amazon.com/NorthPada%C2%AE-Charger-Raspberry-Android-Samsung/dp/B00OY7HR1U/), [Adafruit](https://www.adafruit.com/products/1995))
* Ethernet Cable ([Amazon](http://www.amazon.com/Mediabridge-Cat5e-Ethernet-Patch-Cable/dp/B003O973OA/), [Adafruit](https://www.adafruit.com/products/994))
* 433Mhz Transmitter and Receiver ([Amazon](http://www.amazon.com/gp/product/B00M2CUALS/), [Ebay](http://www.ebay.com/sch/sis.html?_nkw=433Mhz+RF+transmitter+and+receiver+link+kit+for+Arduino+ARM+MCU+WL))
* Etekcity Wireless Outlets ([Amazon](http://www.amazon.com/gp/product/B00DQELHBS/))

###Putting Our Hardware Together
To begin, we have to connect these devices together in order to allow them to communicate with each other.

####Amazon Echo
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Begin by setting up your Amazon Echo using [Amazon's instructions](https://www.amazon.com/gp/help/customer/display.html?nodeId=201601770).
  
####Raspberry Pi (taken from [here](https://www.howtoforge.com/tutorial/howto-install-raspbian-on-raspberry-pi/))

#####Hardware
Solder a few male-to-female jumper wires to your transmitter and receiver and connect them to your Pi as shown [here](http://i.imgur.com/BM1Jq0h.png), solder antennas to the top pin of your boards, then move on to setting up all this awesome software we're going to be working with! 

#####Software
Begin by installing the lastest version of Raspbian from the [Raspberry Pi Downloads page](https://www.raspberrypi.org/downloads/), the follow [their instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to install it to your SD card.

Insert your SD card, plug in your Raspberry Pi and get started!

Please remember that after booting the Pi, there might be situations when the user credentials like the "username" and password will be asked. Raspberry Pi comes with a default user name and password and so always use it whenever it is being asked. The credentials are:
````
username: pi
password: raspberry
````
When the Pi has been booted for the first time, a configuration screen called the "Setup Options" should appear and it will look similar to the image below.

![raspi-config](https://www.howtoforge.com/images/raspbian_basics/big/raspiconfig.png)

>If you have missed the "Setup Options" screen, its not a problem, you can always get it by typing the following command in the terminal.
>````
>sudo raspi-config
>````

Now that the Setup Options window is up, we will have to set up a few things. After completing each of the steps below, if it asks to reboot the Pi, please do so. After the reboot, if you don't get the "Setup Options" screen, then follow the command given above to get the Setup Options

Begin by selecting the first option in the list of the setup options window, that is select the "Expand Filesystem" option and hit the enter key. We do this to make use of all the space present on the SD card as a full partition. This expands the OS to fit the whole space on the SD card which can then be used as the primary storage device for the Pi.

Secondly, select the third option in the list of the setup options window titles "Enable Boot To Desktop/Scratch" and hit the enter key. It will take you to another window called the "choose boot option" window that looks like the image below.

![boot selection](https://www.howtoforge.com/images/raspbian_basics/big/raspiconfig2.png)

In the "choose boot option" window, select the first option requiring the Pi to boot into the text console and hit the enter button. Once done you will be taken back to the "Setup Options" page, if not select the "OK" button at the bottom of this window and you will be taken back to the previous window. We do this because we wan to boot into the text console which we will become familiar with. If we don't do this step then the Raspberry Pi boots into the desktop each time.

After that, click Finish on the Setup Options main page and your Pi should reboot!

Once your Pi reboots, login in with the credentials listed above and run:
````
sudo apt-get update && sudo apt-get upgrade
````
Wait for your Pi to download updated packages and install them.

When that's finished, enter 
````
wget https://git.io/vz5xx -O qs.sh && sudo chmod +x qs.sh && sudo ./qs.sh
````

Then follow the on-screen instructions.

### Congratulations, you're done! Wasn't that easy?
