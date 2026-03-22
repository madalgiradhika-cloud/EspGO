# EspGO

# ESP32 Autonomous Robot

A fully-featured autonomous robot platform with GPS navigation, obstacle avoidance, and enterprise-grade security.

## Features

**Navigation**
- GPS waypoint following with calibration
- Dual-sensor obstacle detection (VL53L0X + HC-SR04)
- PID controller for precise movement
- Waypoint route planning

**Security**
- WPA3 WiFi encryption
- AES-256 data encryption
- JWT token authentication
- MAC address whitelisting
- Rate limiting protection

**Control**
- WebSocket real-time control
- Mobile-friendly web interface
- Manual joystick control
- Autonomous mode with obstacle avoidance

**Monitoring**
- Battery voltage monitoring
- GPS signal quality tracking
- Sensor data logging
- Error logging and recovery

## Hardware Requirements

**Required Components**
- ESP32 Development Board
- L298N Motor Driver
- 4x BO Gear Motors
- NEO-6M GPS Module
- VL53L0X ToF Sensor
- HC-SR04 Ultrasonic Sensor
- 3S LiPo Battery (11.1V)

**Optional Components**
- MPU6050 IMU
- MicroSD Card Module
- OLED Display

## Pin Connections

**L298N Motor Driver**
- GPIO13 (ENA) → ENA
- GPIO12 (IN1) → IN1
- GPIO14 (IN2) → IN2
- GPIO27 (ENB) → ENB
- GPIO26 (IN3) → IN3
- GPIO25 (IN4) → IN4

**Sensors**
- GPIO16 (RX2) → NEO-6M TX
- GPIO17 (TX2) → NEO-6M RX
- GPIO21 (SDA) → VL53L0X SDA
- GPIO22 (SCL) → VL53L0X SCL
- GPIO32 (TRIG) → HC-SR04 TRIG
- GPIO33 (ECHO) → HC-SR04 ECHO
- GPIO35 (ADC) → Battery Monitor

## Installation

**1. Install ESP32 Board**
```bash
# In Arduino IDE
File → Preferences → Additional Board Manager URLs
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json

Tools → Board → Board Manager → Search "ESP32" → Install



TinyGPS++ by Mikal Hart
VL53L0X by Pololu
ArduinoJson by Benoit Blanchon
WebSockets by Markus Sattler
PubSubClient by Nick O'Leary



Select Board: ESP32 Dev Module
Select Port: /dev/ttyUSB0 (or COMx)
Click Upload


const char* ap_ssid = "ESP32_SecureRobot";
const char* ap_password = "SecureP@ssw0rd123!";

const char* ENCRYPTION_KEY = "Your32ByteKeyForAES256!!";
const char* JWT_SECRET = "YourJWTSuperSecretKey";
const char* ADMIN_PASSWORD_HASH = "5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8";

#define MAX_SPEED 220
#define BASE_SPEED 180
#define TURN_SPEED 150


Get App
Here's a comprehensive README.md file with all the details in a neat, organized format:

markdown
# 🤖 ESP32 Autonomous Robot - Complete Documentation

[![Platform](https://img.shields.io/badge/platform-ESP32-blue)](https://www.espressif.com/)
[![Security](https://img.shields.io/badge/security-AES--256%20%7C%20WPA3-green)](https://github.com/)
[![GPS](https://img.shields.io/badge/GPS-NEO--6M-orange)](https://www.u-blox.com/)
[![License](https://img.shields.io/badge/license-MIT-yellow)](LICENSE)

A fully-featured autonomous robot platform based on ESP32 with advanced navigation, obstacle avoidance, and enterprise-grade security.

## 📋 Table of Contents
- [Features](#-features)
- [Hardware Requirements](#-hardware-requirements)
- [Pin Configuration](#-pin-configuration)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage Guide](#-usage-guide)
- [Security Features](#-security-features)
- [API Documentation](#-api-documentation)
- [Testing & Calibration](#-testing--calibration)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features

### Core Capabilities
- **Autonomous Navigation**: GPS waypoint following with PID control
- **Obstacle Avoidance**: Dual-sensor fusion (VL53L0X + HC-SR04)
- **Real-time Control**: WebSocket-based low-latency control
- **Multi-Mode Operation**: Manual, GPS Navigation, Autonomous, Calibration

### Advanced Features
- **📍 GPS Navigation**
  - NEO-6M module with WAAS/EGNOS support
  - Calibration system for improved accuracy (±1-2m)
  - Waypoint route planning (up to 50 waypoints)
  - Real-time position tracking

- **🛡️ Enterprise Security**
  - WPA3 WiFi encryption
  - AES-256 data encryption
  - JWT token authentication
  - MAC address whitelisting
  - Rate limiting & DoS protection

- **📊 Sensor Suite**
  - VL53L0X Time-of-Flight (1200mm range, ±3% accuracy)
  - HC-SR04 Ultrasonic (400cm range, ±3mm accuracy)
  - Battery monitoring (10.5V-12.6V range)
  - IMU integration (MPU6050)

- **🌐 Connectivity**
  - Secure WebSocket (WSS) server
  - MQTT cloud integration
  - OTA firmware updates
  - Data logging to SD card

## 🔧 Hardware Requirements

### Essential Components
| Component | Model | Quantity | Purpose |
|-----------|-------|----------|---------|
| Microcontroller | ESP32 Dev Board | 1 | Main controller |
| Motor Driver | L298N | 1 | 4WD motor control |
| DC Motors | BO Gear Motor | 4 | Drive system |
| GPS Module | NEO-6M | 1 | Navigation |
| ToF Sensor | VL53L0X | 1 | Precision distance |
| Ultrasonic | HC-SR04 | 1 | Long-range detection |
| Battery | 3S LiPo (11.1V) | 1 | Power source |

### Optional Components
| Component | Model | Purpose |
|-----------|-------|---------|
| IMU | MPU6050 | Orientation & stabilization |
| Magnetometer | HMC5883L | Compass heading |
| SD Card Module | MicroSD | Data logging |
| Camera | ESP32-CAM | Computer vision |
| OLED Display | SSD1306 | Status display |
| Buzzer | 5V Active | Audio alerts |

## 📡 Pin Configuration

### Motor Driver (L298N)
ESP32 GPIO → L298N
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
GPIO13 (ENA) → ENA (PWM - Left Motors)
GPIO12 (IN1) → IN1 (Left Forward)
GPIO14 (IN2) → IN2 (Left Backward)
GPIO27 (ENB) → ENB (PWM - Right Motors)
GPIO26 (IN3) → IN3 (Right Forward)
GPIO25 (IN4) → IN4 (Right Backward)

text

### Sensors
ESP32 GPIO → Sensor
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
GPS (UART2):
GPIO16 (RX2) → TX (NEO-6M)
GPIO17 (TX2) → RX (NEO-6M)

VL53L0X (I2C):
GPIO21 (SDA) → SDA
GPIO22 (SCL) → SCL

HC-SR04:
GPIO32 (TRIG) → TRIG
GPIO33 (ECHO) → ECHO

Battery Monitor:
GPIO35 (ADC) → Voltage Divider

Optional - MPU6050 (I2C):
GPIO21 (SDA) → SDA
GPIO22 (SCL) → SCL

Optional - SD Card (SPI):
GPIO4 (CS) → CS
GPIO23 (MOSI)→ MOSI
GPIO19 (MISO)→ MISO
GPIO18 (SCK) → SCK

text

## 🚀 Installation

### 1. Prerequisites
```bash
# Install ESP32 board support
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json

# Required Libraries (install via Arduino Library Manager)
- TinyGPS++ by Mikal Hart
- VL53L0X by Pololu
- ArduinoJson by Benoit Blanchon
- WebSockets by Markus Sattler
- PubSubClient by Nick O'Leary
- MPU6050_tockn by tockn
2. Clone Repository
bash
git clone https://github.com/yourusername/esp32-autonomous-robot.git
cd esp32-autonomous-robot
3. Configure Settings
cpp
// Open config.h and modify:
#define WIFI_SSID "Your_Secure_Network"
#define WIFI_PASSWORD "Your_Strong_Password"
#define ADMIN_PASSWORD_HASH "your_sha256_hash"
#define ENCRYPTION_KEY "Your32ByteKeyForAES256!!"
This response is AI-generated, for reference only.
Give me a short one without any charts
Here's a concise README in neat code-style formatting:

markdown
# ESP32 Autonomous Robot

A fully-featured autonomous robot platform with GPS navigation, obstacle avoidance, and enterprise-grade security.

## Features

**Navigation**
- GPS waypoint following with calibration
- Dual-sensor obstacle detection (VL53L0X + HC-SR04)
- PID controller for precise movement
- Waypoint route planning

**Security**
- WPA3 WiFi encryption
- AES-256 data encryption
- JWT token authentication
- MAC address whitelisting
- Rate limiting protection

**Control**
- WebSocket real-time control
- Mobile-friendly web interface
- Manual joystick control
- Autonomous mode with obstacle avoidance

**Monitoring**
- Battery voltage monitoring
- GPS signal quality tracking
- Sensor data logging
- Error logging and recovery

## Hardware Requirements

**Required Components**
- ESP32 Development Board
- L298N Motor Driver
- 4x BO Gear Motors
- NEO-6M GPS Module
- VL53L0X ToF Sensor
- HC-SR04 Ultrasonic Sensor
- 3S LiPo Battery (11.1V)

**Optional Components**
- MPU6050 IMU
- MicroSD Card Module
- OLED Display

## Pin Connections

**L298N Motor Driver**
- GPIO13 (ENA) → ENA
- GPIO12 (IN1) → IN1
- GPIO14 (IN2) → IN2
- GPIO27 (ENB) → ENB
- GPIO26 (IN3) → IN3
- GPIO25 (IN4) → IN4

**Sensors**
- GPIO16 (RX2) → NEO-6M TX
- GPIO17 (TX2) → NEO-6M RX
- GPIO21 (SDA) → VL53L0X SDA
- GPIO22 (SCL) → VL53L0X SCL
- GPIO32 (TRIG) → HC-SR04 TRIG
- GPIO33 (ECHO) → HC-SR04 ECHO
- GPIO35 (ADC) → Battery Monitor

## Installation

**1. Install ESP32 Board**
```bash
# In Arduino IDE
File → Preferences → Additional Board Manager URLs
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json

Tools → Board → Board Manager → Search "ESP32" → Install
2. Install Required Libraries

bash
TinyGPS++ by Mikal Hart
VL53L0X by Pololu
ArduinoJson by Benoit Blanchon
WebSockets by Markus Sattler
PubSubClient by Nick O'Leary
3. Upload Code

bash
Select Board: ESP32 Dev Module
Select Port: /dev/ttyUSB0 (or COMx)
Click Upload
Configuration
WiFi Settings

cpp
const char* ap_ssid = "ESP32_SecureRobot";
const char* ap_password = "SecureP@ssw0rd123!";
Security Keys

cpp
const char* ENCRYPTION_KEY = "Your32ByteKeyForAES256!!";
const char* JWT_SECRET = "YourJWTSuperSecretKey";
const char* ADMIN_PASSWORD_HASH = "5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8";
Motor Settings

cpp
#define MAX_SPEED 220
#define BASE_SPEED 180
#define TURN_SPEED 150
Usage
1. Power On

Connect battery (11.1V recommended)

Wait for ESP32 boot (blue LED flashing)

2. Connect to WiFi

SSID: ESP32_SecureRobot

Password: SecureP@ssw0rd123!

3. Access Web Interface

Open browser: https://192.168.4.1

Login: admin / password

4. Control Modes

Manual Mode

Use virtual joystick

Adjust speed slider

Real-time response

GPS Navigation

Enter target coordinates

Click "Set Target"

Robot navigates automatically

Autonomous Mode

Robot explores area

Avoids obstacles

Returns to start if lost

Calibration Mode

Place robot in open area

Click "Start GPS Calibration"

Wait 60 seconds stationary

Calibration saves automatically

Security Features
WiFi Security

WPA3 encryption enabled

Hidden SSID option

20MHz bandwidth only

Data Security

AES-256 encrypted commands

JWT tokens expire after 1 hour

HTTPS web server on port 443

WSS WebSocket on port 81

Access Control

MAC address whitelisting

Rate limiting (60 req/sec)

Brute force protection

Session management

GET  /                 - Main control interface
POST /api/login        - Authentication
POST /api/secure       - Encrypted commands
GET  /api/status       - Robot status JSON


WebSocket Commands

json
{"command":"mode", "mode":"manual"}
{"command":"gps_target", "lat":37.7749, "lng":-122.4194}
{"command":"manual", "x":0.5, "y":0.8, "speed":180}
{"command":"start_calibration"}
{"command":"reset_calibration"}


Get App
Here's a concise README in neat code-style formatting:

markdown
# ESP32 Autonomous Robot

A fully-featured autonomous robot platform with GPS navigation, obstacle avoidance, and enterprise-grade security.

## Features

**Navigation**
- GPS waypoint following with calibration
- Dual-sensor obstacle detection (VL53L0X + HC-SR04)
- PID controller for precise movement
- Waypoint route planning

**Security**
- WPA3 WiFi encryption
- AES-256 data encryption
- JWT token authentication
- MAC address whitelisting
- Rate limiting protection

**Control**
- WebSocket real-time control
- Mobile-friendly web interface
- Manual joystick control
- Autonomous mode with obstacle avoidance

**Monitoring**
- Battery voltage monitoring
- GPS signal quality tracking
- Sensor data logging
- Error logging and recovery

## Hardware Requirements

**Required Components**
- ESP32 Development Board
- L298N Motor Driver
- 4x BO Gear Motors
- NEO-6M GPS Module
- VL53L0X ToF Sensor
- HC-SR04 Ultrasonic Sensor
- 3S LiPo Battery (11.1V)

**Optional Components**
- MPU6050 IMU
- MicroSD Card Module
- OLED Display

## Pin Connections

**L298N Motor Driver**
- GPIO13 (ENA) → ENA
- GPIO12 (IN1) → IN1
- GPIO14 (IN2) → IN2
- GPIO27 (ENB) → ENB
- GPIO26 (IN3) → IN3
- GPIO25 (IN4) → IN4

**Sensors**
- GPIO16 (RX2) → NEO-6M TX
- GPIO17 (TX2) → NEO-6M RX
- GPIO21 (SDA) → VL53L0X SDA
- GPIO22 (SCL) → VL53L0X SCL
- GPIO32 (TRIG) → HC-SR04 TRIG
- GPIO33 (ECHO) → HC-SR04 ECHO
- GPIO35 (ADC) → Battery Monitor

## Installation

**1. Install ESP32 Board**
```bash
# In Arduino IDE
File → Preferences → Additional Board Manager URLs
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json

Tools → Board → Board Manager → Search "ESP32" → Install
2. Install Required Libraries

bash
TinyGPS++ by Mikal Hart
VL53L0X by Pololu
ArduinoJson by Benoit Blanchon
WebSockets by Markus Sattler
PubSubClient by Nick O'Leary
3. Upload Code

bash
Select Board: ESP32 Dev Module
Select Port: /dev/ttyUSB0 (or COMx)
Click Upload
Configuration
WiFi Settings

cpp
const char* ap_ssid = "ESP32_SecureRobot";
const char* ap_password = "SecureP@ssw0rd123!";
Security Keys

cpp
const char* ENCRYPTION_KEY = "Your32ByteKeyForAES256!!";
const char* JWT_SECRET = "YourJWTSuperSecretKey";
const char* ADMIN_PASSWORD_HASH = "5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8";
Motor Settings

cpp
#define MAX_SPEED 220
#define BASE_SPEED 180
#define TURN_SPEED 150
Usage
1. Power On

Connect battery (11.1V recommended)

Wait for ESP32 boot (blue LED flashing)

2. Connect to WiFi

SSID: ESP32_SecureRobot

Password: SecureP@ssw0rd123!

3. Access Web Interface

Open browser: https://192.168.4.1

Login: admin / password

4. Control Modes

Manual Mode

Use virtual joystick

Adjust speed slider

Real-time response

GPS Navigation

Enter target coordinates

Click "Set Target"

Robot navigates automatically

Autonomous Mode

Robot explores area

Avoids obstacles

Returns to start if lost

Calibration Mode

Place robot in open area

Click "Start GPS Calibration"

Wait 60 seconds stationary

Calibration saves automatically

Security Features
WiFi Security

WPA3 encryption enabled

Hidden SSID option

20MHz bandwidth only

Data Security

AES-256 encrypted commands

JWT tokens expire after 1 hour

HTTPS web server on port 443

WSS WebSocket on port 81

Access Control

MAC address whitelisting

Rate limiting (60 req/sec)

Brute force protection

Session management

API Endpoints
Web Interface

text
GET  /                 - Main control interface
POST /api/login        - Authentication
POST /api/secure       - Encrypted commands
GET  /api/status       - Robot status JSON
WebSocket Commands

json
{"command":"mode", "mode":"manual"}
{"command":"gps_target", "lat":37.7749, "lng":-122.4194}
{"command":"manual", "x":0.5, "y":0.8, "speed":180}
{"command":"start_calibration"}
{"command":"reset_calibration"}
Testing Procedures
Range Test

Open web interface

Click "Range Test"

Move obstacle away slowly

Note maximum detection distance

GPS Accuracy Test

Place robot at known location

Run GPS calibration

Compare displayed vs actual position

Check accuracy reading (<2m is good)

Battery Test

Fully charge battery (12.6V)

Run robot continuously

Monitor voltage drop

Note runtime until 10.5V

Troubleshooting
No WiFi Connection

Check power supply (min 5V 2A)

Verify AP mode enabled

Reset ESP32 and try again

GPS No Fix

Move to open area

Wait 2-3 minutes for first fix

Check antenna connection

Ensure 4+ satellites visible

Motors Not Moving

Check battery voltage

Verify L298N connections

Test with simple blink code

Check ENA/ENB jumpers

Sensors Not Reading

Verify I2C connections

Check sensor addresses

Run sensor test mode

Replace if defective

Error Codes
Code	Meaning	Solution
E001	GPS No Fix	Move to open area
E002	Low Battery	Charge battery
E003	Motor Overload	Check for obstructions
E004	Sensor Timeout	Check connections
E005	WiFi Error	Restart AP mode
E006	Auth Failed	Check credentials
Maintenance
Daily

Clean sensors with soft cloth

Check wheel alignment

Verify battery charge

Weekly

Calibrate GPS in open area

Test obstacle detection

Update firmware if available

Monthly

Inspect wiring connections

Lubricate motor bearings

Backup configuration data

License
MIT License - Free for personal and commercial use

Support
Documentation: /docs folder

Issues: GitHub Issues

Email: atharvaphadnis8@gmail.com

Forum: quickstore.base44.app

Credits
Developed by [Atharva Phadnis]

Libraries: TinyGPS++, VL53L0X, ArduinoJson, WebSockets

text

This README provides all essential information in a clean, code-style format without charts or complex formatting.


