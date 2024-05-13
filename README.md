# lgpio-GPIO
Wrapper uses the new C-language gpiochip functions in Xojo 2023 r1.1

This is a lgpio local library that is a replacement for the deprecated sysfs library that
is to be used with Xojo apps. This library uses local c language calls, which means updates
should be minimal and your code should be stable for a very long time. 

![](https://github.com/eugenedakin/lgpio-GPIO/blob/main/BlinkSmall.png)

The lgpio library can be installed Raspberry Pi OS (21 Feb 2020) and instructions 
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

As of Apr 2023, the latest Operating System is Raspberry Pi OS with desktop, Kernel version 5.15, Debian version:11 (bullseye), with Raspberry Pi 4B, using Xojo's 2023 R1 (Xojo API2) code. 
On 13 May 2023, the latest Operating System is Raspberry Pi OS with desktop, Kernel version 6.6, Debian version: 12 (Bookworm), with Raspberry Pi 5, using Xojo's 2024 r4.1 (Xojo API2) code.

To use the lgpio with Raspberry Pi 4 or older systems, get the chip handle with the following command:
| Initialize the Raspberry Pi 4 lgpio |
| --------------------------------- |
| MyChipHandle = lgGpiochipOpen(0) //dev/gpiochip0 for Raspberry Pi 4 or older |

To use the lgpio with the Raspberry Pi 5 board, get the chip handle with the following command:
| Initialize the Raspberry Pi 5 lgpio |
| --------------------------------- |
| MyChipHandle = lgGpiochipOpen(4) //dev/gpiochip4 for Raspberry Pi 5 |

With the changes in Raspberry Pi motherboard, Buster Opeating System, Xojo API2, and deprecation
of wiringPi, and sysfs, a new book might be written that provides examples, explanations, and 
data for all of these recent changes. 

Credit is given to Joan at http://abyz.me.uk/lg/lgpio.html who has matured the libgpiod C library with a wrapping of the lgpio C API.

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

V1.3 (12 Mar 2022)
 - Added lgTxPwm method
 - Added InfiniteCycles property 

V1.4 (13 Mar 2022)
 - Added lgTxServo method

V1.5 (27 Mar 2022)
 - Added lguSleep method

V1.6 (17 Apr 2022)
 - Updated lgGpioClaimOutput to have a more descriptive error 
 - Added lguErrorText function 
 - Updated lgGpiochipOpen to have a more descriptive error 
 - Updated lgGpiochipClose to have a more descriptive error 
 - Updated lgGpioClaimInput to have a more descriptive error 
 - Updated lgGpioFree to have a more descriptive error 
 - Updated lgGpioRead to have a more descriptive error 
 - Updated lgGpioWrite to have a more descriptive error 
 - Updated lgTxPwm to have a more descriptive error 
 - Updated lgTxServo to have a more descriptive error 

V1.7 (5 Mar 2023)
 - Fixed Error 

V1.8 (19 Mar 2023)
 - Added lguSleep

V1.9 (25 Mar 2023)
 - Updated Version notes

V1.10 (26 Mar 2023)
 - Added lguTimestamp

V1.11 (2 Apr 2023)
 - Added lgGpioClaimAlert
 - Added LG_RISING_EDGE
 - Added LG_FALLING_EDGE
 - Added LG_BOTH_EDGES
 - Added lgGpioSetAlertsFunc

V1.12 (7 Apr 2023)
 - Added lgTxPulse

V1.13 (28 May 2023)
 - Updated lgTxPwm
 - Added lgI2cClose
 - Added lgI2cOpen
 - Added lgI2cReadByteData
 - Added lgI2cWriteByteData
 - Added lguErrorText

V1.14 (29 May 2023)
 - Added lgI2cReadWordData
 - Added lgI2cWriteWordData
 - Updated comment on lgI2cReadByteData
 - Updated comment on lgI2cWriteByteData
 - Added lgI2cReadBlockData
 - Added lgI2cWriteBlockData

V1.15 (30 May 2023)
 - Added lgI2CWriteQuick
 - Added lgI2cReadByte
 - Added lgI2cWriteByte
 - Added lgI2cReadI2CBlockData
 - Added lgI2cWriteI2CBlockData
 - Added lgI2cReadDevice
 - Added lgI2cWriteDevice
 - Added lgI2cProcessCall
 - Added lgI2cBlockProcessCall
 - Added lgI2cSegments
 - Added lgI2cZip

V1.16 (31 May 2023)
 - Added lguVersion
 - Added lguSbcName
 - Added lguGetInternal
 - Added lguSetInternal
 - Added lguSetWorkDir
 - Added lguGetWorkDir
 - Added LG_CFG_ID_MIN_DELAY
 - Added LG_CFG_ID_DEBUG_LEVEL

V1.17 (3 July 2023)
 - Added lgSpiOpen
 - Added lgSpiClose
 - Added lgSpiRead
 - Added lgSpiWrite
 - Added lgSpiXfer

V1.18 (5 July 2023)
 - Added more descriptive information in lgSpiOpen method
 - Added more descriptive information in lgSpiClose method
 - Added more descriptive information in lgSpiWrite method
 - Edited descriptive information in lgSpiXfer method

V1.19 (8 July 2023)
 - Added LG_GPIO_LABEL_LEN GPIO Constant
 - Added LG_GPIO_NAME_LEN GPIO Constant
 - Added LG_GPIO_USER_LEN GPIO Constant
 - Added lgChipInfo_t Structure 
 - Updated lgI2cWriteBlockData rxBuf to txBuf
 - Added lgGpioGetChipInfo method
 - Added LG_OKAY constant

V1.20 (9 July 2023)
 - Updated lgGpioGetChipInfo information
 - Added lgGpioGetLineInfo method
 - Added lgLineInfo_p structure uses lgLineInfoFlags method
 - Wrote lgLineInfoFlags method to return string from bits
 - Added lgGpioGetMode uses lgLineInfoFlags method
 - Added lgGpioSetUser method
 - Wrote lgGPIOUser structure 
 - Added lgTxBusy
 - Added LG_TX_PWM
 - Added LG_TX_WAVE
 - Added LG_LOW
 - Added LG_HIGH
 - Added LG_TIMEOUT
 - Added LG_GPIO_IS_KERNEL
 - Added LG_GPIO_IS_OUTPUT
 - Added LG_GPIO_IS_ACTIVE_LOW
 - Added LG_GPIO_IS_OPEN_DRAIN
 - Added LG_GPIO_IS_OPEN_SOURCE
 - Added LG_GPIO_IS_PULL_UP
 - Added LG_GPIO_IS_PULL_DOWN
 - Added LG_GPIO_IS_PULL_NONE
 - Added LG_GPIO_IS_INPUT
 - Added LG_GPIO_IS_RISING_EDGE
 - Added LG_GPIO_IS_FALLING_EDGE
 - Added LG_GPIO_IS_REALTIME_CLOCK

V1.21 (10 July 2023)
 - lgI2cWriteDevice fixed unused rxBuf issue
 - lgSpiWrite fixed unused rxBuf issue
 - Added gpio unused parameter in lgGpioFree Method
 - Added PulseWidth in lgTxServo unused method paramter
 - Added eFlags in lgGpioClaimAlert unused method parameter 
 - Placed retval local parameter in used area of lgTxServo

V1.22 (11 July 2023)
 - Added LG_MAX_PATH
 - Added LG_THREAD_NONE
 - Added LG_THREAD_STARTED
 - Added LG_THREAD_RUNNING
 - Added LG_NOTIFY_CLOSED
 - Added LG_NOTIFY_CLOSING
 - Added LG_NOTIFY_RUNNING
 - Added LG_NOTIFY_PAUSED
 - Added MAX_REPORT
 - Added MAX_SAMPLE
 - Added STACK_SIZE
 - Added LG_USER_LEN
 - Added LG_SALT_LEN

V1.23 (12 July 2023)
 - Added LG_FILE_NONE
 - Added LG_FILE_MIN
 - Added LG_FILE_READ
 - Added LG_FILE_WRITE
 - Added LG_FILE_RW
 - Added LG_FILE_APPEND
 - Added LG_FILE_CREATE
 - Added LG_FILE_TRUNC
 - Added LG_FILE_MAX

V1.24 (13 July 2023)
 - Add LG_FROM_START
 - Add LG_FROM_CURRENT
 - Add LG_FROM_END
 - Add LG_SET_REALTIME_CLOCK
 - Add LG_SET_INPUT
 - Add LG_SET_OUTPUT
 - Add LG_MAX_MICS_DEBOUNCE
 - Add LG_MAX_MICS_WATCHDOG
 - Add LG_MAX_MICS_DELAY
 - Add LG_MAX_MILS_DELAY

V1.25 (14 July 2023)
 - Add LG_SCRIPT_INITING 
 - Add LG_SCRIPT_READY   
 - Add LG_SCRIPT_RUNNING 
 - Add LG_SCRIPT_WAITING 
 - Add LG_SCRIPT_EXITED  
 - Add LG_SCRIPT_ENDED   
 - Add LG_SCRIPT_HALTED  
 - Add LG_SCRIPT_FAILED  

V1.26 (15 July 2023)
 - Add LG_I2C_RDRW_IOCTL_MAX_MSGS
 - Add LG_MAX_SPI_DEVICE_COUNT
 - Add LG_MAX_I2C_DEVICE_COUNT
 - Add LG_I2C_END
 - Add LG_I2C_ESC
 - Add LG_I2C_ADDR
 - Add LG_I2C_FLAGS
 - Add LG_I2C_READ
 - Add LG_I2C_WRITE

V1.27 (23 July 2023)
 - Add lgGpioReport_t Structure 
 - Add lgI2cMsg_t Structure
 - Add lgPulse_p Structure 

V1.28 (31 July 2023)
 - Add lgGpioAlert_x Structure
 - Add lgGpioAlertsFunc_t Structure 
