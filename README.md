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

Credit is given to Joan at http://abyz.me.uk/lg/lgpio.html who has matured the libgiod C library with a wrapping of the lgpio C API.

V1.0 (22 Dec 2020)
  The initial and starting declares used to work with the lgpio on Raspberry Pi 4,
with Xojo 2021 r3.1, with the Raspberry Pi OS. As the writing
of the new book progresses, so will the versions of this class. 

V1.1 (6 Mar 2022)
 - Changed the format of lgpio module to be consistent with long-term development
 - Changed lgGpiochipOpen method internals
 - Changed lgGpiochipClose method internals
 - Changed lgGpioClaimOutput method internals
 - Changed lgGpioWrite method internals
 - Added lgGpioInfo method
 - Added On Property 
 - Added OFF Property 
 - Added HIGH Property 
 - Added Low Property 
 - Added lgGpioFree method
 - Added LG_SET_ACTIVE_LOW property 
 - Added LG_SET_OPEN_DRAIN property 
 - Added LG_SET_OPEN_SOURCE property 
 - Added LG_SET_PULL_DOWN property 
 - Added LG_SET_PULL_NONE property 
 - Added LG_SET_PULL_UP property 

V1.2 (7 Mar 2022)
 - Added lgGpioClaimInput method
 - Added lgGpioRead method
