# NotYetBuddy - Realtime USB Forensics Tool

---

## Features

- Real-time USB detection (device inserted/removed)
- Extracts device name, VID, and PID
- Logs all USB events with date/time stamps
- Flags **known malicious USB devices**
- Simple C++17 implementation using Win32 API
- Future-ready for USB power (TDP) monitoring
- Lightweight and fast; no external dependencies

---

## Use Cases

- Cybersecurity research
- USB activity auditing
- Intrusion detection for keystroke injection devices (Rubber Ducky, Bash Bunny)
- Physical access monitoring in sensitive environments
- Forensics and compliance tracking

---

## Requirements

- **Platform**: Windows 10 / 11 (x64)
- **Compiler**: MSVC with C++17 support
- **Build Tool**: Visual Studio 2019/2022
- **Linked Libraries**:  
  - `SetupAPI.lib`  
  - `Cfgmgr32.lib`

---

## Project Structure

```plaintext
NotYetBuddy/
├── src/
│   ├── main.cpp
│   ├── usb_utils.cpp
│   ├── usb_logger.cpp
│   ├── usb_monitor.cpp
│   └── usb_jail_terminal.cpp
│
├── include/
│   ├── usb_utils.h
│   ├── usb_logger.h
│   ├── usb_monitor.h
│   └── usb_jail_terminal.h
│
├── logs/
│   ├── usb_events.log
│   └── jail_terminal.txt
│
└── README.md
```
---

## Known Malicious USB Signatures

| VID:PID      | Device                          |
|--------------|----------------------------------|
| 05AC:8300    | BadUSB (Apple Internal)         |
| 1D6B:0104    | Rubber Ducky (USB Gadget)       |
| 1D50:6089    | Bash Bunny                      |
| 0FC5:B080    | HID Keyboard Injection (Hak5)   |
| 322E:202C    | NOT_M5 Stick                    |
| 13D3:3563    | Bluetooth Adapter               |
| 0403:6001    | FT232R USB UART                 |

---

## Sample Log Output

[2025-06-04 14:21:10] USB Connected - Bluetooth Adapter (13D3:3563) [Bluetooth Adapter]
[2025-06-04 14:25:47] USB Connected - Generic Flash Drive (0781:5567) [Normal USB]
[2025-06-04 14:27:55] USB Connected - Unknown HID Device (1D6B:0104) [Rubber Ducky (USB Gadget)]

---

## Future Roadmap

### USB Power (TDP) Logging
- Monitor and log real-time USB port power draw
- Detect power anomalies during device injection

### Intelligent Event Classification
- Behavior-based detection of suspicious HID activity
- Logging "jailed" keystrokes from unauthorized input devices

### GUI Dashboard
- Real-time USB device view
- TDP and event graphing

### Kernel Mode Driver
- Protection against low-level USB rootkits and stealthy firmware attacks

---

## Developed By
Madhav Tyagi
Cybersecurity Researcher

## Mentor
Dr. Rakshit Tandon

## Timeline
- Conceived at IntrusionX National Cybersecurity Hackathon
- Built and extended as part of GPCSSI 2025 Internship
- Continues as a real-world USB threat monitoring and research tool

“Let the ducks quack. We jail them.” – NotYetBuddy
