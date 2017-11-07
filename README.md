# Basic IoT scenario
This is example based on [Basic IoT scenario lab in Introduction to informatics course](https://wiki.itcollege.ee/index.php/Category:I600_Introduction_to_Computers_and_Informatics#Assignment:_Set_up_basic_IoT_scenario) for TTÜ IT College Cyber Security Engineering first year students.

## Prerequisites
* A WeMos Lolin32 microcontroller with at least one color led
* [pip](https://pip.pypa.io/en/stable/)
* picocom ``sudo apt-get install picocom``.
* wget ``sudo apt-get install wget``.
* esptool ``pip install esptool``
* Adafruit-ampy ``pip install adafruit-ampy``.

## How to use
### Flashing MicroPython

Install MicroPython:
```
wget http://micropython.org/resources/firmware/esp32-20171017-v1.9.2-279-g090b6b80.bin
esptool.py -p /dev/ttyUSB0 -b 460800 erase_flash
esptool.py -p /dev/ttyUSB0 -b 460800 write_flash --flash_mode dio 0x1000 esp32-*.bin
```

### Get the microcontroller ready

Upload files to ESP32:
```
ampy -p /dev/ttyUSB0 put boot.py
ampy -p /dev/ttyUSB0 put main.py
```

### Run it
Connect through picocom:
```
picocom -b115200 /dev/ttyUSB0
```


Run the code:
```
main()
```

Enter the shown ip into the browser and start blinking.
