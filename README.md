LoRa Mesh Network for Real-Time Atmospheric Monitoring
This project demonstrates the implementation of mesh networks using LoRa (Long Range) modules integrated with microcontrollers to monitor and analyze real-time atmospheric conditions. Developed and deployed as part of an IoT-based system at RRSC-West, Jodhpur Centre, ISRO, the system enables reliable long-range, low-power communication for enhanced weather data collection and prediction.

📡 Overview
Communication Technology: LoRa (433 MHz)

Architecture: Mesh-style communication using unique device addresses

Microcontroller: Arduino-compatible boards

Use Case: Real-time sensing and transmission of climatic parameters

Deployment Site: RRSC West, ISRO Jodhpur

🚀 Features
Duplex LoRa communication

Assignable device addresses (for multi-node mesh routing)

Periodic data broadcast (every 2–3 seconds)

Message integrity checks

RSSI and SNR diagnostics for quality monitoring

📁 Folder Structure
bash
Copy
Edit
.
├── lora_mesh_node.ino      # Main Arduino sketch
├── README.md               # This file
🧰 Hardware Requirements
LoRa SX1278 module (433 MHz)

Arduino Uno / Nano / Mega or compatible board

Connecting wires / breadboard

Sensors (optional): DHT11/22, BMP180, etc. for atmospheric data

Power supply or battery pack

🔧 Pin Configuration (Example)
Function	Arduino Pin
LoRa CS (NSS)	D7
LoRa RESET	D6
LoRa IRQ (DIO0)	D1 (INT)

⚠️ IRQ pin must support external interrupt.

📟 Code Overview
Initialization
cpp
Copy
Edit
LoRa.setPins(csPin, resetPin, irqPin);
LoRa.begin(433E6);  // Set to 433 MHz
Sending a Message
cpp
Copy
Edit
sendMessage("HeLoRa World!");
Each message packet includes:

Destination address

Sender address

Message ID

Payload length

Actual message

Receiving a Message
Handled using:

cpp
Copy
Edit
onReceive(LoRa.parsePacket());
Performs:

Header parsing

Length verification

Message filtering (based on address)

RSSI and SNR reporting

🔄 Example Serial Output
yaml
Copy
Edit
Sending HeLoRa World!
Received from: 0xbb
Sent to: 0xff
Message ID: 1
Message length: 13
Message: HeLoRa World!
RSSI: -72
Snr: 9.5
📡 Mesh Network Scalability
You can deploy multiple nodes using unique localAddress values (e.g., 0xAA, 0xBB, 0xCC, ...), and configure the destination for point-to-point or broadcast (0xFF) communication.

For actual mesh routing (hop-by-hop), an additional layer of routing logic can be added using message forwarding based on a routing table.

🧪 Future Improvements
Integrate environmental sensors (DHT22, BMP280)

Add mesh routing protocols (e.g., AODV-lite for LoRa)

Store data locally using SD card

Push data to cloud via LoRa-to-Gateway bridge

🛰️ Developed At
ISRO RRSC-West, Jodhpur
Date: Jun 24, 2024
Domain: Internet of Things (IoT), Wireless Sensor Networks, Environmental Monitoring

📜 License
MIT License. Feel free to use, modify, and deploy for educational and research purposes.

