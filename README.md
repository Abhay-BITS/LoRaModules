

# 🌐 LoRa Mesh Network for Real-Time Atmospheric Monitoring

**Implementation of Mesh Networks of Long-Range (LoRa) Modules for Real-time Monitoring of Atmospheric Conditions using Internet-of-Things (IoT) Devices**  
📍 **ISRO RRSC-West, Jodhpur**  
📅 **June 24, 2024**  
🔧 **Domain**: IoT, Wireless Sensor Networks, Environmental Monitoring

---

## 📡 Overview

This project demonstrates the implementation of **LoRa mesh networks** integrated with **Arduino microcontrollers** for real-time, long-range, low-power monitoring of **atmospheric conditions**. The system is designed for **deployment in field environments** where internet connectivity may be limited or unavailable.

---

## 🚀 Features

- Duplex LoRa communication with message acknowledgment
- Node addressing for multi-node mesh scalability
- Broadcast support for simple mesh topologies
- Real-time diagnostics via RSSI and SNR
- Message integrity verification

---

## 🔧 Hardware Requirements

- LoRa SX1278 (433 MHz) module
- Arduino Uno/Nano/Mega (or equivalent)
- Jumper wires / breadboard
- Optional: Environmental sensors (e.g., DHT22, BMP180)
- Power supply / battery pack

---

## ⚙️ Pin Configuration

| Function         | Arduino Pin |
|------------------|-------------|
| LoRa CS (NSS)    | D7          |
| LoRa RESET       | D6          |
| LoRa IRQ (DIO0)  | D1 (INT)    |

> **Note**: IRQ pin must be a hardware interrupt-capable pin.

---

## 💻 Code

The core functionality is in the `lora_mesh_node.ino` file. The device:

- Initializes the LoRa module at 433 MHz
- Sends a simple message every 2–3 seconds
- Parses incoming packets
- Verifies headers and payload integrity
- Prints RSSI, SNR, and message metadata via Serial Monitor

### ✉️ Example Message Output

```

Sending HeLoRa World!
Received from: 0xbb
Sent to: 0xff
Message ID: 1
Message length: 13
Message: HeLoRa World!
RSSI: -72
Snr: 9.5

```

---

## 📁 Folder Structure

```

.
├── lora\_mesh\_node.ino      # Main Arduino sketch
├── README.md               # Project documentation

```

---

## 🌍 Mesh Scalability

To create a **multi-node network**:
- Assign each node a unique `localAddress` (e.g., `0xAA`, `0xBB`, `0xCC`)
- Use `0xFF` for broadcasting messages to all nodes
- Optionally, implement routing logic for hop-based relaying

> Future work includes support for routing tables and message forwarding.

---

## 🔮 Future Enhancements

- 🌡️ Integrate real-time sensors (DHT22, BMP280)
- 🧠 Add routing algorithms (e.g., simplified AODV)
- 💾 Store logs on SD card
- ☁️ Add LoRa-to-Gateway node for cloud integration

---

## 🛰️ Developed At

**Remote Sensing Applications Centre (RRSC-West)**  
**Indian Space Research Organisation (ISRO)**  
Jodhpur, India

---

## 📜 License

MIT License. Free to use, modify, and distribute for academic and research purposes.

---

## 🙋‍♂️ Contributors

- Abhay & Divynash – Developer  
- ISRO RRSC-West Team – Mentors and Field Deployment  

