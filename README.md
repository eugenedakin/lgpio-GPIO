# lgpio-GPIO
Wrapper uses the new C-language gpiochip functions in Xojo 2020 r2.1

This is a lgpio local library that is a replacement for the deprecated sysfs library that
is to be used with Xojo apps. This library uses local c language calls, which means updates
should be minimal and your code should be stable for a very long time. 

![](https://github.com/eugenedakin/lgpio-GPIO/blob/main/BlinkSmall.png)

The lgpio library can be installed Raspberry Pi OS (Dec 2020) and instructions 
are available at http://abyz.me.uk/lg/download.html

Install instructions are:
1) sudo apt install swig python-dev python3-dev
2) sudo apt install python-setuptools python3-setuptools
3) wget http://abyz.me.uk/lg/lg.zip
4) unzip lg.zip
5) cd lg
6) make
7) sudo make install
8) create a Blink example program and copy the program and libraries to the RaspberryPi Desktop
9) give the executable permission to run with something like: 'sudo chmod +x Blink'
10) run the program with something like: 'sudo ./Blink'

As of Dec 2020, the latest Operating System is Raspbian Buster, with Raspberry Pi 4B, 
using Xojo's 2020 R2.1 (Xojo API2) code. 

With the changes in Raspberry Pi motherboard, Buster Opeating System, Xojo API2, and deprecation
of wiringPi, and sysfs, a new book might be written that provides examples, explanations, and 
data for all of these recent changes. 
