Demo project for STM32F407ZET6 and TFT LCD 240x320.

Working with the display using FSMC 16 bit. CS_MAIN - FSMC_NE4. RS - FSMC_A6.
FSMC Memory Bank1 NOR/PSRAM. Data address 0x6C000080, Command address 0x6C000000.

The backlight of the display is controlled by pin PB 15. Can use PWM.

Drivers for working with ili9341 are located in the ili9341 folder.
Display initialization taken from https://narodstream.ru/stm-urok-37-displej-tft-240x320-8bit-chast-3/. 

Files lcd_work.h and lcd_work.c contain a custom library for drawing geometric shapes, symbols, numbers and strings on the display.

The STemWin library is connected. When building a project with the help of gcc (for example using CUBEMX_IDE), you must include the library file from ST in the project, for example STemWin_CM4_wc32.a. Before its name it is necessary to put :

An example of setting up a project to include a library file:
![Image alt](https://github.com/NKP144/stm32_tft_lcd/blob/master/ScreenShots/Adding%20STemWin%20lib.png)

When building with the STemWin library, the lsd_work.c file must be excluded from the build, otherwise there will be a conflict of function names.