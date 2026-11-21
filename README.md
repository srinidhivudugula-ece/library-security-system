Overview

The **Library Security System** is an automated embedded system designed to improve library security, monitor book movements, and authenticate students without requiring continuous manual supervision.
The system uses an ESP32 microcontroller, GM65 barcode scanner, load cell, and HX711 amplifier to identify students, detect book removals, and validate book transactions.
Students can use their existing college ID card barcodes for identification, while books are identified using their ISBN barcodes.
The system monitors weight variations on library shelves and checks whether book removal is associated with an authorized student and a valid book barcode.
Visual and audio alerts are generated whenever unauthorized activities or invalid transactions are detected.
The project also incorporates an IoT communication concept using Wi-Fi, Google Sheets and Telegram notifications for remote monitoring and transaction logging.

Problem Statement

Traditional departmental libraries often depend on manual supervision to maintain book security and manage student access.
The absence of continuous monitoring creates several challenges:
- Unauthorized removal of library books.
- Difficulty tracking student entry and exit.
- Manual effort required for maintaining transaction records.
- Limited availability of library monitoring facilities.
- Risk of book loss due to insufficient supervision.
This project proposes a low-cost automated security solution using barcode identification and weight-based book monitoring.

Project Objectives

- Develop an automated library security system.
- Authenticate students using existing college ID barcodes.
- Identify books using ISBN barcodes.
- Detect book removal through continuous weight monitoring.
- Validate student and book information before checkout.
- Generate alerts for unauthorized book removal.
- Display real-time system status through an LCD.
- Provide visual and audible security indications.
- Explore IoT-based remote monitoring and transaction logging.


System Block Diagram

       STUDENT ID BARCODE
                |
                v
        GM65 BARCODE SCANNER
                |
                |
                v
          +-----------+
          |           |
          |   ESP32   | <----- HX711 <----- LOAD CELL
          |           |
          +-----------+
                |
          +-----+------+
          |            |
          v            v
       I2C LCD       IR SENSOR
          |
          |
     +----+------+
     |           |
     v           v
     green led   red led
                   | 
                   v
                   buzzer 
       ESP32 Wi-Fi
            |
      +-----+------+
      |            |
      v            v
      Google Sheets  Telegram

Software Requirements

- Arduino IDE
- ESP32 Board Package
- Embedded C/C++
- ESP32 Wi-Fi Library
- HX711 Library
- LiquidCrystal_I2C Library
- Wire Library
- HTTPClient Library
- WiFiClientSecure Library

Advantages

- Reduces dependence on manual supervision.
- Uses existing student ID and book barcodes.
- Provides automated book removal detection.
- Combines identification and weight monitoring.
- Provides visual and audible security alerts.
- Uses an affordable embedded-system architecture.
- Supports expansion towards IoT-based monitoring.

 Current Limitations
 
- A single load-cell channel cannot independently identify multiple books removed simultaneously.
- Weight drift and mechanical vibrations can affect detection accuracy.
- The prototype requires appropriate calibration.
- The current student and book registration lists are limited.
- Network-based logging depends on Wi-Fi availability.
- Reliable deployment requires further validation of the checkout and exit synchronization logic.

Future Scope

- Integration with Firebase or an SQL database.
- Real-time administrator dashboards.
- Improved cloud-based student authentication.
- Offline transaction storage and automatic synchronization.
- Multiple load-cell channels for individual shelf monitoring.
- Advanced book inventory management.
- Improved sensor filtering and calibration.
- Enhanced access control and automated library management.

