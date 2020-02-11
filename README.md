# Raspberry Pi Arduino Communication

The function of this code is to be able to pass messages between a Raspberry Pi and an Arduino. This setup has the Raspberry Pi as the master and the Arduino as a slave.

![Diagram](https://raw.githubusercontent.com/himalayanelixir/Arduino_RaspberryPi_Ping/master/images/Arduino_RaspberryPi_Ping.png)

# Instructions

## Raspberry Pi
 
 1. Requirements: Need Python 3 and pyserial. pyserial can be installed using pip. 

    ```
    pip install -r Raspberry\ Pi/requirements.txt
    ```

 3. You will likely have to modify the `serPort = "/dev/cu.SLAB_USBtoUART"` line in the code to match which port your Arduino will be located on. 

 2. Run

    ```
    python3 Raspberry\ Pi/controller.py
    ```

 3. Enter commands using the format `<Up,Down,Left,Right>`. Currently the code is made to look for `< >` at the beginning and end of commands and different commands are separated by a comma. 


 ## Arduino

1. Open the project in the Arduino IDE by clicking on `Arduino/Arduino.ino`

2. There are 3 files in this project. 
    
    - Arduino.ino - Contains the `setup()` and `loop()` functions 
    - arduino_controller_functions.ino - This is where the magic happens. The `ProcessData()` function is where you will be adding logic to execute commands from the Raspberry Pi.
    - communications.ino - Contains the logic to communicate with the Raspberry Pi over serial. 

3. Upload your code to the Arduino. Currently no matter what commands are sent to the Arduino it will flash the built-in LED and return a success message to the Raspberry Pi. 
