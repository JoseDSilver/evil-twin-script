# evil-twin-script
C++ firmware for ESP32-S3 implementing a standalone Rogue Access Point for wireless security auditing.
# ESP32-S3 Wireless Security Assessment Firmware

This repository contains a C++ implementation of a Rogue Access Point (Evil Twin) designed for the ESP32-S3 architecture. It serves as a Proof of Concept (PoC) for educational purposes and wireless security auditing.

## Project Overview

The firmware leverages the ESP32-S3 Wi-Fi capabilities to simulate access points, manage client connections, and host a captive portal. The project focuses on low-level implementation using the ESP-IDF framework / Arduino Core.

## Hardware Requirements

1. **Microcontroller:** ESP32-S3 (Recommended: ESP32-S3-WROOM-1U for external antenna support).
2. **Antenna:** 2.4GHz external antenna with IPEX/U.FL connector (if using the 1U module).
3. **Power Supply:** External 5V PSU or LiPo battery (recommended minimum 500mA output for stable Wi-Fi transmission).

## Features

* SSID Broadcasting and Beacon Frame generation.
* DNS Spoofing (Captive Portal redirection).
* HTTP Server for credential harvesting simulation.
* Management of multiple client connections.
* Serial interface for logging and control.

## Installation

### Prerequisites

* Visual Studio Code
* PlatformIO (recommended) or Arduino IDE
* C++17 support enabled

### Build and Flash

1. Clone the repository:
   git clone https://docs.github.com/pt/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github

2. Open the project in PlatformIO.

3. Configure the `platformio.ini` file according to your specific board revision.

4. Build and upload the firmware:
   pio run --target upload

5. Monitor the serial output:
   pio device monitor --baud 115200

## Usage

1. Power on the device.
2. The ESP32 will verify the antenna connection and initialize the Wi-Fi stack.
3. Access the Serial Monitor to view the IP address and client connection logs.
4. On a victim device, connect to the target SSID.
5. The captive portal should trigger automatically.

## Disclaimer

This software is for educational purposes and authorized security auditing only. The author is not responsible for any misuse of this code. Ensure you have explicit permission from the network owner before running this firmware.

## License

MIT License
