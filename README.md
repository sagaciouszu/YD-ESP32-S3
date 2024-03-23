# Google Autotranslated

# YD-ESP32-S3 Core Board

###### Introduction:

The YD-ESP32-S3 core board is designed by VCC-GND Studio. If necessary, you can visit www.vcc-gnd.com to purchase it. This device uses the ESP32-S3 chip, which can be used for testing prototypes of Internet of Things applications and can also be used for practical applications. It is equipped with two USBs, one is a hardware USB-to-serial port (CH343P WCH Qinheng), and the other is ESP32-S3 USB port.

![](/IMG/img1.PNG)

This guide will help you quickly get started with YD-ESP32-S3 and provide detailed information about this development board.

YD-ESP32-S3 is an entry-level development board equipped with Wi-Fi + Bluetooth® LE module ESP32-S3-WROOM-1.

Most of the pins of the on-board module have been led out to the pin headers on both sides of the development board. Developers can easily connect various peripheral devices through jumpers according to actual needs, or the development board can be plugged into a breadboard for use.
![img](/IMG/YD-ESP32-S3.PNG)

1. This is the minimum core board of ESP32-S3, using the ESP32-S3 module of Espressif Systems.
2. LDO circuit dedicated for wireless function, no need to worry about insufficient current (power).
3. Equipped with a WS2812-RGB LED (note that it is not lit directly through GPIO).
4. The RST button is used for the external reset function and the boot button (with the rst button, it can be booted into the bootloard mode. After reset, it can be used as a user button, which is GPIO0).
5. You will find that the board has two TYPE-C interfaces (one is directly connected to USB (GPIO19 GPIO20), and the other is a USB port for USB to serial port), equipped with a hardware USB to serial port chip (CH343).

###### Hardware introduction:

![](/IMG/img2.png)

| Main Components | Introduction |
| :--------------------------------------- | -------- -------------------------------------------------- -- |
| ESP32-S3-WROOM-1 | ESP32-S3-WROOM-1 is a universal Wi-Fi + low-power Bluetooth MCU module with rich peripheral interfaces, powerful neural network computing capabilities and signal processing capabilities. Built for the artificial intelligence and AIoT market. ESP32-S3-WROOM-1 uses a PCB on-board antenna. |
| 5 V to 3.3 V LDO (5 V to 3.3 V LDO) | Power converter, input 5 V, output 3.3 V, current 1A |
| Pin Headers | All available GPIO pins (except the flash SPI bus) have been led out to the development board's pin headers. |
| USB-to-UART Port (USB to UART interface) | Type-c-USB interface, which can be used as the power supply interface of the development board, can be used to burn firmware to the chip, and can also be used as a communication interface through the onboard USB to UART bridge. The device communicates with the chip. |
| Boot Button | Download button. Press and hold the **Boot** key and press the **Reset** key to enter the "firmware download" mode and download the firmware through the serial port. If it is started, it can be used as an ordinary input button, and the IO used is GPIO0. |
| Reset Button | Reset button. |
| USB Port (USB interface) | ESP32-S3 USB OTG interface, supporting the full-speed USB 1.1 standard. The ESP32-S3 USB interface can be used as the power supply interface of the development board, can burn firmware to the chip, communicate with the chip through the USB protocol, and can also be used for JTAG debugging. |
| USB-to-UART Bridge | The chip is CH343P, the manufacturer is Qinheng, the website is http://www.wch-ic.com/, the driver is: http://www.wch-ic. com/products/CH343.html? |
| RGB LED | Addressable RGB light-emitting diode driven by GPIO48. The model number is WS2812. |
| PWR LED | Power indicator light. It lights up after the board is powered and cannot be controlled by the program. |
| TX LED | The LED on the serial port TXD line of ESP32-S3. When serial port data is sent, the LED flashes. If the serial port function is not used, it can be used as GPIO, GPIO43 |
| RX LED | The LED on the serial port RXD line of ESP32-S3. When serial port data is received, the LED flashes. If the serial port function is not used, it can be used as GPIO, GPIO44 |



###### Remark:

On development boards with onboard ESP32-S3-WROOM-1 module series (using 8-wire SPI flash/PSRAM), pins GPIO35, GPIO36 and GPIO37 have been used for communication between the internal ESP32-S3 chip and SPI flash/PSRAM. , not available externally.



###### Start developing the application:
Before powering on, please ensure that the development board is intact.



###### Functional block diagram:
The main components and connection methods of YD-ESP32-S3 are shown in the figure below:

![](/IMG/img4.png)



###### Power options:
You can choose one of the following three power supply methods to power the development board:

Powered by USB to UART interface or powered by ESP32-S3 USB interface (select one or both), default power supply method (recommended)

Powered by 5V and G (GND) pin headers

3V3 and G (GND) pin header power supply

###### Pin:
The following table lists the names and functions of the pin headers (P1 and P2) on both sides of the development board. The names of the pin headers are shown in the figure on the front of YD-ESP32-S3. The serial numbers of the pin headers are consistent with the development board schematic diagram (PDF).

###### P1

| Serial number | Name | Type | Function |
| ---- | ---- | ----- | ---------------------------------- -------------------------- |
| 1 | 3V3 | P | 3.3 V power supply |
| 2 | 3V3 | P | 3.3 V power supply |
| 3 | RST | I | EN |
| 4 | 4 | I/O/T | RTC_GPIO4, GPIO4, TOUCH4, ADC1_CH3 |
| 5 | 5 | I/O/T | RTC_GPIO5, GPIO5, TOUCH5, ADC1_CH4 |
| 6 | 6 | I/O/T | RTC_GPIO6, GPIO6, TOUCH6, ADC1_CH5 |
| 7 | 7 | I/O/T | RTC_GPIO7, GPIO7, TOUCH7, ADC1_CH6 |
| 8 | 15 | I/O/T | RTC_GPIO15, GPIO15, U0RTS, ADC2_CH4, XTAL_32K_P |
| 9 | 16 | I/O/T | RTC_GPIO16, GPIO16, U0CTS, ADC2_CH5, XTAL_32K_N |
| 10 | 17 | I/O/T | RTC_GPIO17, GPIO17, U1TXD, ADC2_CH6 |
| 11 | 18 | I/O/T | RTC_GPIO18, GPIO18, U1RXD, ADC2_CH7, CLK_OUT3 |
| 12 | 8 | I/O/T | RTC_GPIO8, GPIO8, TOUCH8, ADC1_CH7, SUBSPICS1 |
| 13 | 3 | I/O/T | RTC_GPIO3, GPIO3, TOUCH3, ADC1_CH2 |
| 14 | 46 | I/O/T | GPIO46 |
| 15 | 9 | I/O/T | RTC_GPIO9, GPIO9, TOUCH9, ADC1_CH8, FSPIHD, SUBSPIHD |
| 16 | 10 | I/O/T | RTC_GPIO10, GPIO10, TOUCH10, ADC1_CH9, FSPICS0, FSPIIO4, SUBSPICS0 |
| 17 | 11 | I/O/T | RTC_GPIO11, GPIO11, TOUCH11, ADC2_CH0, FSPID, FSPIIO5, SUBSPID |
| 18 | 12 | I/O/T | RTC_GPIO12, GPIO12, TOUCH12, ADC2_CH1, FSPICLK, FSPIIO6, SUBSPICLK |
| 19 | 13 | I/O/T | RTC_GPIO13, GPIO13, TOUCH13, ADC2_CH2, FSPIQ, FSPIIO7, SUBSPIQ |
| 20 | 14 | I/O/T | RTC_GPIO14, GPIO14, TOUCH14, ADC2_CH3, FSPIWP, FSPIDQS, SUBSPIWP |
| 21 | 5V | P | 5 V power supply |
| 22 | G | G | Ground |

###### P2

| Serial number | Name | Type | Function |
| ---- | ---- | ----- | ---------------------------------- ------------------ |
| 1 | G | G | Ground |
| 2 | TX | I/O/T | U0TXD, GPIO43, CLK_OUT1 |
| 3 | RX | I/O/T | U0RXD, GPIO44, CLK_OUT2 |
| 4 | 1 | I/O/T | RTC_GPIO1, GPIO1, TOUCH1, ADC1_CH0 |
| 5 | 2 | I/O/T | RTC_GPIO2, GPIO2, TOUCH2, ADC1_CH1 |
| 6 | 42 | I/O/T | MTMS, GPIO42 |
| 7 | 41 | I/O/T | MTDI, GPIO41, CLK_OUT1 |
| 8 | 40 | I/O/T | MTDO, GPIO40, CLK_OUT2 |
| 9 | 39 | I/O/T | MTCK, GPIO39, CLK_OUT3, SUBSPICS1 |
| 10 | 38 | I/O/T | GPIO38, FSPIWP, SUBSPIWP |
| 11 | 37 | I/O/T | SPIDQS, GPIO37, FSPIQ, SUBSPIQ |
| 12 | 36 | I/O/T | SPIIO7, GPIO36, FSPICLK, SUBSPICLK |
| 13 | 35 | I/O/T | SPIIO6, GPIO35, FSPID, SUBSPID |
| 14 | 0 | I/O/T | RTC_GPIO0, GPIO0 |
| 15 | 45 | I/O/T | GPIO45 |
| 16 | 48 | I/O/T | GPIO48, SPICLK_N, SUBSPICLK_N_DIFF, RGB LED |
| 17 | 47 | I/O/T | GPIO47, SPICLK_P, SUBSPICLK_P_DIFF |
| 18 | 21 | I/O/T | RTC_GPIO21, GPIO21 |
| 19 | 20 | I/O/T | RTC_GPIO20, GPIO20, U1CTS, ADC2_CH9, CLK_OUT1, USB_D+ |
| 20 | 19 | I/O/T | RTC_GPIO19, GPIO19, U1RTS, ADC2_CH8, CLK_OUT2, USB_D- |
| 21 | G | G | Ground |
| 22 | G | G | Ground |

P: power supply; I: input; O: output; T: can be set to high impedance.

###### Pin diagram:

![](/IMG/img11.jpg)

###### CH340 chip driver official link:

http://www.wch-ic.com/products/CH340.html?ENGLISH

https://www.wch.cn/products/CH340.html?from=list Chinese

Micropython firmware download:

The download and erase tool software flash_download_tool_3.9.2_0 for ESP32-S3 is download tool under win.
Note: There is no need to install and decompress. Double-click the small gear logo, select ESP32-S3, develop, USART, and look at the rest of the picture. Note that the starting address is 0x00, and there is a check mark in front. If it cannot be downloaded, it may be that the USB to serial port driver is not installed properly. Fix the driver problem first and then download.

![](/IMG/img3.png)

Notice:

You cannot use the so-called ESP32 downloader that comes with thonny to download micropython firmware for ESP32-S3 (the one that comes with thonny is for esp32, the model is not esp32-s3, and the address is not 0x00 of S3 but 0x1000 of ESP32), nor You cannot use the SPRAM firmware officially downloaded by micropython, and it cannot be used normally after downloading. The correct download method is to use Espressif's official flash tool download tool, select ESP32-S3 serial port download (USART), insert the USB into the COM port of the board, and select The starting address of the corresponding firmware (the firmware we adapted from the source) is 0x00. Check the box before selecting the firmware. It is best to erase it first and then download it.
The firmware is a link that starts with 1- and the firmware download software is a link that starts with 2-. Please note that it is best to update the CH343usb to serial port hardware driver before use. Note that in the data link that starts with 0-, confirm that it appears in the device manager. Only if...CH343 is marked COM.

If you download TASMOTA firmware, TASMOTA officially has its own web download.

https://tasmota.github.io/docs/

If you download your own firmware files you can use Espressif's download tool.

https://www.espressif.com.cn/en/home

This text is the information of ESP32-S3. Basic information includes (hardware serial port CH343 driver, source version micropython firmware, software for downloading firmware, micropython IDE, schematic size diagram, etc.): http://124.222.62.86/yd-data/YD-ESP32-S3/

If you plan to use the official idf-C language programming details link (the routine is the API reference): https://docs.espressif.com/projects/esp-idf/zh_CN/latest/esp32s3/get-started/index. html

If you plan to use Ardiuno programming materials link: https://docs.espressif.com/projects/arduino-esp32/en/latest/getting_started.html#about-arduino-esp32

If you plan to use micropython language programming materials, the link is as follows (note that for a quick start, just look at ESP32): https://docs.micropython.org/en/latest/esp32/quickref.html
###### Problems with copycats/counterfeits/low-quality imitations:

There are many copycat/counterfeit/low-quality imitations of our origin (YD) development boards, and Shenzhen Huaqiangbei is the most rampant. The common method used by copycats is to directly polish our development boards and take photos and copy them, resulting in many hidden dangers in copycat products. Now we summarize the dangers (hidden dangers) of buying fake boards.
Take the YD-ESP32 (ESP32/S2/S3/C3) series as an example:

1. In order to further pursue profits, copycat manufacturers often use refurbished and unofficial devices, arbitrarily replacing them with cheap models of the same package, and randomly selecting models for profit.

2. The 2812 lamp does not weld the signal and cannot be used. This proves from the side that the plagiarists do not check the board to save trouble and reduce costs.

3. Counterfeit boards are not inspected before leaving the factory (to reduce costs). They are packaged as soon as they come off the production line and sent to consumers, saving links and maximizing profits.

4. Due to plagiarized photos and many silk screen printing errors, counterfeit boards can easily mislead consumers, and the plagiarists themselves cannot understand them.

5. The copied version of the copycat board is version 1.2, which is an early version in 2022, and the genuine version is version 1.4. The copycat board cannot use the updated functions, so it saves trouble and does not improve.

6. The copycat board uses a third-party "copycat" module (low cost). The copycat module has not been impedance matched. When using WIFI Bluetooth, the power consumption is high, the signal is poor, and it is easy to crash.

7. Since we can’t find our dedicated LDO on the market for copycat boards, we randomly choose inappropriate models, such as 1117 (low cost), which have large pressure differences, are prone to crashes, and have poor signals.

8. The counterfeit board uses diodes with high voltage difference (greater than 0.7V tube voltage drop, low cost), resulting in insufficient back-end LDO voltage difference, further causing high power consumption, easy crash, and poor signal.

9. The copycat board does not provide basic technology, and even the information is directly copied from ours (the information is still from our early days, and the copycats are too lazy to find the latest information). After receiving the money, they don’t care.

10. Sometimes there is a problem when starting the copycat board. It directly enters the BootLoader, making it unusable. The copycat board does not understand what the problem is!

11. Because the counterfeit boards are copied from photos, there are no schematics, which makes users unable to understand how to use them, and neither do the counterfeiters, making the product difficult to use.


Some counterfeiters directly print the words YD-ESP32 and other words on the counterfeit boards to confuse the public. What's worse, some even print our official website WWW.VCC-GND.COM on the counterfeit products. This behavior has triggered relevant laws. , we will definitely pursue the case, please consumers do not covet a few cents ~ a few yuan to bear the above risks, waste time and energy in vain, support the source and support genuine products, please look for the source when purchasing, VCC-GND trademark .

###### Any function on the pin can be realized through the internal switching matrix:

In the introduction of various ESP32 series documents, it is noted that it has various peripheral communication functions such as I2C, I2S, UART, SPI, etc. However, the schematic diagram of the function pins does not indicate which pins these functions are. This question is answered in the peripheral pin allocation. Peripheral interfaces such as I2C, I2S, UART, and SPI can be defined as any GPIO pin, so there is no need to mark it on the functional diagram. Anyway, any GPIO can be These peripheral interface I2C, I2S, UART, and SPI pins can be given certain pin functions.



