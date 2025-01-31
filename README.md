# ESP32-C6 Zigbee Light Bulb Example

This repository contains an example code to flash an ESP32-C6 and enable Zigbee functionality, allowing it to be discovered as an on/off light bulb. This project is designed to be used with PlatformIO.

## Prerequisites

Before getting started, ensure you have the following installed on your machine:

- [PlatformIO](https://platformio.org/) (recommended for dependency management and flashing)
- [ESP-IDF](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/index.html) (if you prefer using ESP-IDF directly)
- An ESP32-C6 with Zigbee-compatible firmware
- A development environment configured for PlatformIO (e.g., VSCode with the PlatformIO extension)

## Repository Structure

- `src/`: Contains the application source code.
- `include/`: Contains header files.
- `partitions.csv`: Partition table file for the ESP32-C6.
- `platformio.ini`: PlatformIO configuration file.

## Flashing the ESP32-C6

### 1. Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/technoo10201/esp32-c6-zigbee-example-platformio
cd esp32-c6-zigbee-example-platformio
```

### 2. Configure PlatformIO

Open the project in VSCode with PlatformIO. Ensure the platformio.ini file is properly configured for your environment.

### 3. Flash the Partitions

Before flashing the code, you need to flash the partitions to the ESP32-C6.
Use the following command in the PlatformIO terminal:
```bash
pio run --target uploadfs
```

This will flash the partitions defined in partitions.csv to the ESP32-C6.

### 4. Flash the Code

Once the partitions are flashed, you can flash the code to the ESP32-C6 using the following command:
```bash
pio run --target upload
```

### 5. Monitor the Output

To view the logs from the ESP32-C6, use the following command:
```bash
pio device monitor
```

### Zigbee Light Bulb Discovery

Once the code is flashed, the ESP32-C6 should be discovered as a Zigbee light bulb in your Zigbee network.
You can use a Zigbee control application (such as Zigbee2MQTT or a compatible app) to interact with the light bulb.
Example Code

The main code is located in src/main.cpp. It implements a basic Zigbee light bulb with the following features:

- Turn the light bulb on/off
- Respond to Zigbee commands
