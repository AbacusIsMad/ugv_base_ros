![GitHub top language](https://img.shields.io/github/languages/top/effectsmachine/ugv_base_ros) ![GitHub language count](https://img.shields.io/github/languages/count/effectsmachine/ugv_base_ros)
![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/effectsmachine/ugv_base_ros)
![GitHub repo size](https://img.shields.io/github/repo-size/effectsmachine/ugv_base_ros) ![GitHub](https://img.shields.io/github/license/effectsmachine/ugv_base_ros) ![GitHub last commit](https://img.shields.io/github/last-commit/effectsmachine/ugv_base_ros)

# Waveshare UGV Robots
This is a lower computer example for the [Waveshare](https://www.waveshare.com/) UGV robots with ROS Driver: **UGV Rover**, **UGV Beast**, **RaspRover**, **UGV02**\*.
**Please see the original repo for more details**

## Compile and upload
### Libraries and environment
The image has been built (and thus confirmed to work) with the following configs:
* Arduino IDE 2.3.2
* esp32 3.0.2 by Espressif Systems (board manager)
    * Do not choose "Arduino ESP32 Boards"!
    * You should choose your project board to be `ESP32 Dev Module`
And the following libaries:
* ArduinoJson 7.1.0
* *LittleFS* 2.0.0
* *FS* 2.0.0
* *WiFi* 2.0.0
* *NetWorking* 1.0.0
* *WebServer* 2.0.0
* Adafruit SSD1306 2.5.10
* Adafruit GFX Library 1.11.10
* Adafruit BusIO 1.16.1
* *Wire* 2.0.0
* *SPI* 2.0.0
* INA219_WE 1.3.8
* ESP32Encoder 0.11.6
* PID_v2 2.0.1
* SimpleKalmanFilter 0.1
* SparkFun 9DoF IMU Breakout - ICM 20948 - Arduino Library 1.2.12

Libraries in *italic* are included by default in the esp32 boards.

### Uploading
You should use the "Export Compiled Binary" option to generate binaries at the current directory. This is stored in the `build` directory.

To upload to the board, you should use the included `flash_download_tool` (for windows).
1. You should set the board name to `ESP32`.
2. You should **always** keep a backup on the current firmware using the "develop" mode of the tool. Refer to https://docs.espressif.com/projects/esp-at/en/latest/esp32/Get_Started/Downloading_guide.html, section "Flash AT Firmware into Your Device", on how to do so.
3. The `build` directory should contain a `...ino.merged.bin`. This is the file we want to flash.
4. Go into into "factory" mode. Uncheck `LockSettings` and change the 4 default files to path of the merged binary, and set its address to `0`.
    * If you do not change anything, the tool will flash v0.93 onto the board.
5. Select the correct `COM` port and an appropriate baud rate, and flash.
6. Disconnect your device and restart the robot. Check if it works.

# License
ugv_base_ros for the Waveshare UGV Robots: an open source robotics platform for the Robots based on **ROS Driver**.
Copyright (C) 2024 [Waveshare](https://www.waveshare.com/)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/gpl-3.0.txt>.
