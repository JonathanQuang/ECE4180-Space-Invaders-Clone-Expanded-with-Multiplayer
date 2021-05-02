# Authors
Jonathan Quang and Daniel Martin


# Overview
Our project is a clone of the classic arcade game (based on Devon Cooper's and Sidak Dhillon's clone), Space Invaders, but with some additional features over other mbed clones. The basic features we have are a joystick that moves the player's ship, a button to fire bullets from the ship, and a LCD screen to display the game. However, our clone boasts some additional feature over other mbed clones. We have added functionality for second player that can connect to the game over a bluetooth module using the Bluefruit Connect app on a Bluetooth enabled phone. Additionally, we added sound effects (with adjustable volume) and LED effects to improve immersion into the game. We have also added a player vs player gamemode, a way to track score and lives, a game over menu with some music, and a starting menu to select gamemodes and to manage the connection of both players.

# Hardware
We used the parts mentioned below. The only part not from the ECE lab is the joystick axis sensor. It outputs vertical and horizontal movement as well as a button press signals. The hardware setup is outlined in the circuit diagram. Basically, the mbed is communicating with all the other modules. The mbed gets its sensor data from the joystick sensor and bluetooth module. The mbed sends data out to the LEDs, the LCD screen, and the Amp chip. The Amp receives power directly from the 5V power supply with its volume being adjusted by the potentiometer. 

- [mbed LPC1768](https://os.mbed.com/platforms/mbed-LPC1768/)
- [Sparkfun PCB speaker 8ohm .1W](https://os.mbed.com/users/4180_1/notebook/tpa2005d1-class-d-audio-amp/)
- [TI TPA2005D1 class D audio amp chip (250Khz PWM)](https://os.mbed.com/users/4180_1/notebook/tpa2005d1-class-d-audio-amp/)
- [uLCD-144-G2](https://os.mbed.com/users/4180_1/notebook/ulcd-144-g2-128-by-128-color-lcd/)
- [KY-023 PS2 joystick axis sensor](https://arduinomodules.info/ky-023-joystick-dual-axis-module/)
- [Adafruit Bluefruit BLE board](https://os.mbed.com/users/4180_1/notebook/adafruit-bluefruit-le-uart-friend---bluetooth-low-/)
- [5v 2AC adapter](https://www.digikey.com/en/products/detail/wurth-electronics-inc/694106301002/5047522?utm_adgroup=Barrel%20-%20Power%20Connectors&utm_source=google&utm_medium=cpc&utm_campaign=Shopping_Product_Connectors%2C%20Interconnects_NEW&utm_term=&utm_content=Barrel%20-%20Power%20Connectors&gclid=Cj0KCQjw-LOEBhDCARIsABrC0TlTFUNaJdsN-9aJB1ibh7JMV1RMs3MJ0_6Dr17MpBX6kMGLQGHtjRsaAuz2EALw_wcB)
- [10K ohm breadboard trim potentiometer](https://www.sparkfun.com/products/9806)
- Red and Blue LEDs with two 330 Ohm Resistors

# Circuit Connections

| Mbed Pin  | TPA2005D1 | 5V 2A AC adapter | Speaker |Potentiometer|
|-----------|-----------|------------------|---------|-------------|
| GND       | pwr-, in- | GND              |         |             | 
|           | pwr+      | Positive         |         |             |
| p21 (PWM) | in+       |                  |         |             |
|           | out+      |                  | +       |             |
|           | out-      |                  | -       |             |
|           | vol+      |                  |         |fixed end 1  |
|           | vol gain  |                  |         |variable end |
|           | vol-      |                  |         |fixed end 2  |



| Mbed Pin | LCD Pin |
|----------|---------|
| p27      | RX      |
| p28      | TX      |
| p30      | RES     |
| GND      | GND     |
| VU       | +5V     |

| Mbed Pin | KY-023 |
|----------|--------|
| GND      | GND    |
| VU (5v)  | +5v    |
| p15      | VRx    |
| p16      | VRy    |
| p22      | SW     |

| Mbed Pin      | Bluetooth BLE Board |
|---------------|---------------------|
| GND           | GND                 |
| VU (5v)       | Vin (3.3-16v)       |
| No connection | RTS                 |
| GND           | CTS                 |
| p14           | TXO                 |
| p13           | RXI                 |


| Mbed Pin | Red LED with Resistor in Series | Blue LED with Resistor in Series |
|----------|---------------------------------|----------------------------------|
| GND      | negative end                    | negative end                     |
| p20      | positive end                    |                                  |
| p24      |                                 | positive end                     |


![Circuit](https://jonathanquang.github.io/ECE4180-Space-Invaders-Clone-Expanded-with-Multiplayer/circuit_diagram.png)

# Code For Project

Code can be found ![here](https://os.mbed.com/users/dmartin99/code/space_invaders_pvp/)!


# Demo of Project

<iframe width="560" height="315" src="https://www.youtube.com/embed/fE4YTzcqwzs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Video of Presentation

<iframe width="560" height="315" src="https://www.youtube.com/embed/4VOGihjKd9A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Images of Project

![Collage](https://jonathanquang.github.io/ECE4180-Space-Invaders-Clone-Expanded-with-Multiplayer/menu_collage.png) 
![Menu](https://jonathanquang.github.io/ECE4180-Space-Invaders-Clone-Expanded-with-Multiplayer/space_menu.jpg) 
![Blue](https://jonathanquang.github.io/ECE4180-Space-Invaders-Clone-Expanded-with-Multiplayer/space_blue.jpg) 
![Shoot](https://jonathanquang.github.io/ECE4180-Space-Invaders-Clone-Expanded-with-Multiplayer/space_shoot.jpg) 


# Code Repositories Used

[Devon Cooper's and Sidak Dhillon's Space Invaders Clone](https://os.mbed.com/users/DNoved1/code/Space_Invaders_Clone/)

[Playing Songs via PWM](https://os.mbed.com/users/4180_1/code/song_demo_PWM/)

# Future Work
- Include more gamemodes
- Improve audio system to support .wav files loaded from an SD card.
- Include other methods of user input, such as a gyroscope
- Add ways to play over the internet with the Ethernet module

There are certainly more features we would add to our project if our group had more time. We were thinking about other game modes besides the classic space invaders and player versus player game modes. For example, a gamemode where both players compete over who can shoot the most aliens or another gamemode where the aliens move in an unpredictable manner. We can also attempt to add more vertical movement and it make the game more similar to other bullet-hell games.  We were also planning to play more complex sounds via WAV files loaded onto an SD card. We currently have a speaker that plays tones based on hardcoded duration and frequency values. The project could also have additional players connect and control ships using other hardware components, like a gyroscope. In addition, the project could have internet connectivity supplied via an ethernet or wifi module so multiplayer is not restricted to players within the immediate vicinity of the mbed chip.
