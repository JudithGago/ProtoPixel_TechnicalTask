# Control the light

This application shows how to build a controller that can turn on and off the board’s embedded LED light of an ESP32 Adafruit Feather board, using wireless commands with a test client. 

## How to use the project

### Configure, Build and Flash 

Build the project and flash it to the board, then run the monitor tool to view the serial output:

1. First the user should select an Espressif target (esp32, esp32s2, etc.) with the **ESP-IDF: Set Espressif device target** command. Default is `esp32` and the one used in this tutorial.

2. Next configure your project using menuconfig. Use the **ESP-IDF: SDK Configuration editor** command (<kbd>CTRL</kbd> <kbd>E</kbd> <kbd>G</kbd> keyboard shortcut ) where the user can modify the ESP-IDF project settings.

  In the `Example Configuration` menu:

   * Set the Wi-Fi configuration.
       * Set `WiFi SSID`.
       * Set `WiFi Password`.

   >Optional: If you need, change the other options according to your requirements. After all changes are made, click save and close this window

3. Configure the `.vscode/c_cpp_properties.json` as explained in [C/C++ Configuration](../C_CPP_CONFIGURATION.md).

4. Now to build the project, use the **ESP-IDF: Build your project** command (<kbd>CTRL</kbd> <kbd>E</kbd> <kbd>B</kbd> keyboard shortcut). The user will see a new terminal being launched with the build output and a notification bar with Building Project message until it is done then a Build done message when finished. You could modify the behavior of the build task with `idf.cmakeCompilerArgs` for Cmake configure step and `idf.ninjaArgs` for Ninja step. For example, using  `[-j N]` where N is the number of jobs run in parallel.

5. Before flashing the project, the user needs to specify the serial port of the device with the **ESP-IDF: Select port to use** command (<kbd>CTRL</kbd> <kbd>E</kbd> <kbd>P</kbd> keyboard shortcut). You can choose between UART/JTAG flashing mode and then a list of serial ports will be shown for the user to select.

> **NOTE:** Please take a look at [ESP-PROG board the instructions](https://docs.espressif.com/projects/espressif-esp-iot-solution/en/latest/hw-reference/ESP-Prog_guide.html#step-by-step-instruction) or [Configuring ESP32 Target](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-guides/jtag-debugging/index.html#configuring-esp32-target) your Espressif device and JTAG interface to your computer.

6. Now to flash the project, use the **ESP-IDF: Flash your project** command (<kbd>CTRL</kbd> <kbd>E</kbd> <kbd>F</kbd> keyboard shortcut). Choose `UART` or `JTAG` flash mode ([Configure JTAG flashing](#About-JTAG-flashing)) and then flashing will start in the previously selected serial port. The user can also use the **ESP-IDF: Flash (UART) your project** or **ESP-IDF: Flash (with JTag)** directly.
  > **NOTE:** When using the **ESP-IDF: Select Flash Method and Flash** command, your choice will be saved in the `idf.flashType` configuration setting.

The user will see a new terminal being launched with the flash output and a notification bar with `Flashing Project` message until it is done then a Flash done message when finished.

7. Now to start monitoring your device, use the **ESP-IDF: Monitor your device** command (<kbd>CTRL</kbd> <kbd>E</kbd> <kbd>M</kbd> keyboard shortcut). The user will see a new terminal being launched with the `idf.py monitor` output.

## Next steps

You can debug ESP-IDF projects as shown in the [debug tutorial](./debugging.md).

The **ESP-IDF: Open ESP-IDF Terminal** will launch a system terminal with ESP-IDF, ESP-IDF tools and ESP-IDF python virtual environment loaded as environment variables. Just typing `idf.py` or `esptool.py` should work to execute scripts from ESP-IDF and additional frameworks.

See other [ESP-IDF extension features](../FEATURES.md).
