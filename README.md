# ESP8266-TinyConfig 📡

![ESP8266 TinyConfig](https://img.shields.io/badge/ESP8266%20TinyConfig-v1.0.0-blue.svg)
![GitHub Release](https://img.shields.io/badge/Releases-latest-orange.svg)

Welcome to the **ESP8266-TinyConfig** repository! This library allows you to easily store and manage configuration data for your ESP8266 projects. Whether you're building an IoT device or just need to manage credentials, this library simplifies the process.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## Features

- **Easy Configuration Storage**: Store configuration data such as Wi-Fi credentials and device settings with ease.
- **Lightweight**: Designed specifically for the ESP8266, it keeps your memory usage low.
- **Flexible**: Supports various data types and structures, making it adaptable for different projects.
- **Arduino IDE and PlatformIO Support**: Works seamlessly with both environments, allowing you to choose your preferred development setup.

## Installation

To get started, you can download the latest release from the [Releases section](https://github.com/Utku1545/ESP8266-TinyConfig/releases). Download the file and include it in your Arduino or PlatformIO project.

### Arduino IDE

1. Open the Arduino IDE.
2. Go to **Sketch** > **Include Library** > **Add .ZIP Library**.
3. Select the downloaded `.zip` file.

### PlatformIO

Add the following line to your `platformio.ini` file:

```ini
lib_deps = Utku1545/ESP8266-TinyConfig
```

## Usage

To use the ESP8266-TinyConfig library, include it in your project:

```cpp
#include <TinyConfig.h>
```

### Basic Setup

Here’s a simple example to get you started:

```cpp
#include <TinyConfig.h>

TinyConfig config;

void setup() {
    Serial.begin(115200);
    
    // Initialize configuration
    config.begin();
    
    // Set Wi-Fi credentials
    config.set("wifi_ssid", "your_SSID");
    config.set("wifi_password", "your_PASSWORD");
    
    // Save configuration
    config.save();
}

void loop() {
    // Your main code
}
```

### Retrieving Configuration

To retrieve the stored configuration, use the `get` method:

```cpp
String ssid = config.get("wifi_ssid");
String password = config.get("wifi_password");
```

## Examples

The library comes with several examples to help you get started quickly. You can find them in the `examples` folder. Here are a few highlights:

### Wi-Fi Credentials Example

This example demonstrates how to store and retrieve Wi-Fi credentials:

```cpp
#include <TinyConfig.h>

TinyConfig config;

void setup() {
    Serial.begin(115200);
    config.begin();
    
    // Set credentials
    config.set("wifi_ssid", "MyNetwork");
    config.set("wifi_password", "MyPassword");
    config.save();
    
    // Retrieve and print
    Serial.println(config.get("wifi_ssid"));
    Serial.println(config.get("wifi_password"));
}

void loop() {
    // Main code here
}
```

### Device Settings Example

This example shows how to store device-specific settings:

```cpp
#include <TinyConfig.h>

TinyConfig config;

void setup() {
    Serial.begin(115200);
    config.begin();
    
    // Set device settings
    config.set("device_name", "ESP8266_Device");
    config.set("update_interval", "60000"); // 60 seconds
    config.save();
    
    // Retrieve and print
    Serial.println(config.get("device_name"));
    Serial.println(config.get("update_interval"));
}

void loop() {
    // Main code here
}
```

## Contributing

We welcome contributions to the ESP8266-TinyConfig library. If you would like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your branch and create a pull request.

Please ensure your code follows the existing style and includes comments where necessary.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Support

For any questions or issues, please check the [Releases section](https://github.com/Utku1545/ESP8266-TinyConfig/releases) for updates or reach out via GitHub issues.

## Acknowledgments

- Thanks to the Arduino community for their continuous support.
- Special thanks to the contributors who help improve this library.

## Conclusion

The **ESP8266-TinyConfig** library provides a straightforward solution for managing configuration data on your ESP8266 projects. With its easy installation and flexible usage, you can focus on building your IoT applications without worrying about configuration management.

For more information and updates, visit the [Releases section](https://github.com/Utku1545/ESP8266-TinyConfig/releases). Happy coding!