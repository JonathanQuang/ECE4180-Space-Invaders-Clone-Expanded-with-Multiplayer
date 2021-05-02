## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/JonathanQuang/ece4180Project/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

#Space Invaders Clone


#Overview
Our project is a clone of the classic arcade game, Space Invaders, but with some additional features over other mbed clones. The basic features we have are a joystick that moves the player's ship, a button to fire bullets from the ship, and a LCD screen to display the game. However, our clone boasts some additional feature over other mbed clones. 
Namely we have added some sound effects played via a speaker with an amp and a second player that can connect to the game over a bluetooth module using the Bluefruit Connect app on a Bluetooth enabled phone. 

#Hardware
- [mbed LPC1768] (https://os.mbed.com/platforms/mbed-LPC1768/)
- [Sparkfun PCB Speaker 8ohm .1W](https://os.mbed.com/users/4180_1/notebook/tpa2005d1-class-d-audio-amp/)
- [TI TPA2005D1 class D audio amp chip (250Khz PWM)](https://os.mbed.com/users/4180_1/notebook/tpa2005d1-class-d-audio-amp/)
- [uLCD-144-G2] (https://os.mbed.com/users/4180_1/notebook/ulcd-144-g2-128-by-128-color-lcd/)
- [KY-023 PS2 joystick axis sensor] (https://arduinomodules.info/ky-023-joystick-dual-axis-module/)
- [Adafruit Bluefruit BLE board](https://os.mbed.com/users/4180_1/notebook/adafruit-bluefruit-le-uart-friend---bluetooth-low-/)
- [5v 2AC Adapter](https://www.digikey.com/en/products/detail/wurth-electronics-inc/694106301002/5047522?utm_adgroup=Barrel%20-%20Power%20Connectors&utm_source=google&utm_medium=cpc&utm_campaign=Shopping_Product_Connectors%2C%20Interconnects_NEW&utm_term=&utm_content=Barrel%20-%20Power%20Connectors&gclid=Cj0KCQjw-LOEBhDCARIsABrC0TlTFUNaJdsN-9aJB1ibh7JMV1RMs3MJ0_6Dr17MpBX6kMGLQGHtjRsaAuz2EALw_wcB)
-[10K Ohm Breadboard Trim Potentiometer](https://www.sparkfun.com/products/9806)



#Circuit Connections
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

| Mbed Pin      | Bluetooth BLE Board |
|---------------|---------------------|
| GND           | GND                 |
| VU (5v)       | Vin (3.3-16v)       |
| No connection | RTS                 |
| GND           | CTS                 |
| p14           | TXO                 |
| p13           | RXI                 |


# Code Repositories Used:
[Devon Cooper's Space Invaders Clone](https://os.mbed.com/users/DNoved1/code/Space_Invaders_Clone/)
[Playing Songs via PWM](https://os.mbed.com/users/4180_1/code/song_demo_PWM/)






### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/JonathanQuang/ece4180Project/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
