## 📡 MorseNet: IoT-Based Optical & Haptic Morse Code Decoder

An edge-powered IoT communication system engineered to bridge legacy telegraphy and modern web networks. Utilizing low-latency microcontroller hardware alongside optical and tactile sensors, the device samples, filters, and decodes incoming Morse signals in real time, synchronizing the translated plaintext directly with a cloud dashboard.

⚡ Key Highlights

🟢 Multi-Modal Input Capture: Accurately decodes signals from physical telegraph keys, optical laser pulses, and audio tone inputs via edge GPIO interrupts.

🟢 Edge Timing & Calibration: Onboard adaptive thresholding distinguishes dots, dashes, and letter gaps to handle varying manual transmission speeds.

🟢 Real-Time Cloud Telemetry: Bridges physical transmissions to the web using lightweight MQTT and WebSocket protocols with minimal latency.

🟢 Dual-Output Visualization: Delivers instant local feedback on a 0.96-inch OLED display while simultaneously streaming live buffers to an interactive web console.

🟢 Accessible Emergency Signaling: Provides a lightweight, reliable fallback channel for low-bandwidth communication and assistive input environments.
## 🙏 Acknowledgements

The successful completion of this project, "IoT-based Morse Code Decoder," would not have been possible without the guidance, encouragement, and support of several individuals and institutions. I express my sincere gratitude to all of them.

🎓 Project Guide & Mentor: I extend my heartfelt gratitude to my project guide, [Aparup Banerjee], [Associate engineer], IIMCIP TIC, for their invaluable mentorship, technical insights, and continuous encouragement throughout the design and implementation phases of this system.

🏛️ Head of the Department & Institution: I am deeply thankful to [Sankha Ray], [IIMCIP TIC], and the administration of Academy of Technology for granting access to the necessary laboratory resources, testing facilities, and computational infrastructure.

🔬 Laboratory & Technical Staff: My appreciation goes to the laboratory instructors and technical staff of the [IoT/Embedded Systems/Electronics] Lab for their timely assistance with hardware components, sensor calibration, and debugging tools.

🤝 Peer Support & Collaboration: I am grateful to my batchmates and friends for their constructive feedback, creative suggestions, and moral support during the integration of the hardware and web interface.

💡 Open-Source & Developer Community: I would also like to acknowledge the global open-source community, particularly the developers behind the ESP microcontroller libraries, MQTT brokers, and web standards, whose resources and documentation made this project feasible.

👨‍👩‍👧 Family: Finally, I owe an immense debt of gratitude to my parents and family for their unwavering faith, patience, and encouragement throughout my academic journey.



Rajesh Mondal
- Member ID: BCL-AOT-0109
- Build Club
- IIMCIP TIC
- Academy of Technology, Adisaptagram
## API Reference

#### Get all items

```http
  GET /api/items
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. 🔑 X-402-Nonce|

#### Get item

```http
  GET /api/items/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. 🔏 X-402-Proof |



## 📑 Appendix

📋 Morse Timing Reference:

- Dot (.): 1 unit of time.
- Dash (-): 3 units of time.
- Intra-character space: 1 unit.
- Letter space: 3 units.
- Word space: 7 units.

🔌 Default GPIO Pins:

- Button / Sensor Pin: GPIO 4
- Buzzer Output: GPIO 5
- OLED I2C SDA: GPIO 21 / SCL: GPIO 22

## Color Reference

| Color             | Hex                                                                |
| ----------------- | ------------------------------------------------------------------ |
| Example Color | ![#0a192f](https://dummyimage.com/10/0a192f/white?text=+) #0a192f |
| Example Color | ![#f8f8f8](https://dummyimage.com/10/f8f8f8/white?text=+) #f8f8f8 |
| Example Color | ![#00b48a](https://dummyimage.com/10/00b48a/white?text=+) #00b48a |
| Example Color | ![#00d1a0](https://dummyimage.com/10/00d1a0/white?text=+)) #00d1a0 |
## 🤝 Contributing

Contributions are always welcome!

Contributions, issues, and feature requests from the open-source agentic commerce community are welcome!

	1.	🍴 Fork the Project
	2.	🌿 Create your Feature Branch (git checkout -b feature/AdaptiveTimingAlgorithm)
	3.	📝 Commit your Changes (git commit -m 'Add adaptive debounce filter')
	4.	🚀 Push to the Branch (git push origin feature/AdaptiveTimingAlgorithm)
	5.	🔀 Open a Pull Request with detailed test notes.
    
Please ensure all TypeScript (@morse_code_decoder-sdk) and Python (morse_code-sdk) changes include unit tests for replay protection and spend-cap enforcement.


## 🚀 Deployment


1. Deploy the Interactive Web Showcase (index.html)
Because index.html is a self-contained single-file application, it deploys in seconds with zero build configuration:

```
# Deploy via Vercel CLI
npx vercel --prod

# Deploy via Netlify CLI
npx netlify deploy --prod --dir=.

```

2. Deploy the Full Backend Stack (Docker Compose)
```
⚬	☁️ Web Dashboard: Deploy static dashboard files directly to Vercel, GitHub Pages, or Netlify.
⚬	📡 MQTT Broker: Deploy a Mosquitto broker on an AWS EC2 micro instance or use cloud brokers like HiveMQ Cloud or EMQX.
⚬	💾 On-Chip Web Server: Upload index.html directly to the ESP32 SPIFFS / LittleFS flash filesystem to serve pages offline without internet access.


```
## 📚 Documentation

📑 Hardware Schematic: Detailed pin connections in /docs/schematics.pdf.

📝 Timing Specifications: International Morse standard timing breakdown in /docs/timing-spec.md.

🌐 Web API Docs: Socket protocol and payload schema in /docs/websocket-api.md.

## ⚙️ Environment Variables
To run this project, configure the following variables in config.h or .env:

- 📶 WIFI_SSID: 2.4 GHz wireless network name.
- 🔑 WIFI_PASSWORD: Wi-Fi network password.
- 🌐 MQTT_BROKER: IP address or domain of the MQTT broker (e.g., broker.emqx.io).
- 🔌 MQTT_PORT: Broker port (1883 for TCP, 8083 / 8084 for WebSockets).
- 📢 MQTT_TOPIC_DECODE: MQTT topic for publishing decoded text (iot/morse/decoded).
- ⏱️ BASE_UNIT_MS: Standard Morse dot unit duration (default: 120).
## ✨ Features

🔴 Edge-Based Signal Processing: Zero cloud lag; signal timing calculation happens directly on the microcontroller.

⏱️ Adaptive WPM Tuning: Automatically adjusts to user typing speed variations (dot vs. dash timing thresholds).

🔄 Bi-Directional Telemetry: Sends live input buffers and decoded sentences over MQTT & WebSockets.

🎛️ Dual Display: Live preview on an onboard SSD1306 0.96" OLED screen and web dashboard simultaneously.

🔊 CW Sidetone Audio Feedback: Generates real-time 750 Hz buzzer and Web Audio feedback.
## 📥 Installation
📥 Clone Repository:

```bash
  git clone https://github.com/your-username/morse-code-decoder-iot.git
cd morse-code-decoder-iot
```

📦 Install Firmware Dependencies:

- Install VS Code + PlatformIO extension (or Arduino IDE).
- Install libraries: PubSubClient, Adafruit SSD1306, Adafruit GFX Library.
- 🖥️ Install Web Dependencies:

```bash
  cd web-dashboard
npm install
```
    
## 💡 Lessons Learned

⚡ Switch Debouncing: Hardware and software debouncing (15–20 ms) is vital to avoid duplicate dots.

⏱️ Non-Blocking Logic: Avoided delay() in firmware; used millis() timers to prevent packet loss.

📶 MQTT Latency: Lightweight JSON payloads reduce transmission latency to under 30 ms over standard Wi-Fi.

## 📄 Licence

⚖️ Released under the MIT License. See LICENSE file for details.

## 🔗 Related Projects

📻 WebAudio-CW-Generator: Browser-based Morse sound synthesizer.

⚡ ESP-MQTT-Base: Reusable lightweight template for ESP8266/ESP32 MQTT nodes.

📡 LoRa-Morse-Relay: Long-range off-grid text transmission network.


## 🗺️ Roadmap

📍 Phase 1: Hardware keying, edge timing decoding, and OLED output (Completed).

📍 Phase 2: MQTT integration and live web simulator dashboard (Completed).

📍 Phase 3: Machine learning / AI model for noisy optical pulse classification.

📍 Phase 4: Two-way communication (Text-to-Morse audio buzzer playback).
## 💻 Run Locally

🔌 Flash Edge Firmware:
- Connect ESP32/ESP8266 via Micro-USB.
- Open the /firmware folder in PlatformIO.
- Upload firmware: pio run --target upload.
- Open serial monitor at 115200 baud to verify IP and Wi-Fi status.

🌐 Launch Web Interface:

```bash
  python3 -m http.server 8000
```


## 🛟 Support

💬 Discussions: Open a GitHub Issue for bug reports or hardware pinout queries.

📧 Email: letsmailrajeshmondal@gmail.com

📖 FAQ: Check documentation for common baud rate and Wi-Fi disconnect solutions.
## 🛠️ Tech Stack

🎛️ Hardware / Edge: ESP32 / ESP8266 NodeMCU, LDR Optical Sensor, Push Button, SSD1306 I2C OLED, Piezo Buzzer.

💻 Embedded Firmware: C++ / Arduino IDE / PlatformIO, PubSubClient, Adafruit GFX / SSD1306.

🌐 Frontend / Web UI: HTML5, Vanilla JavaScript, CSS3, Web Audio API.

📡 Protocols & Broker: MQTT (Mosquitto / HiveMQ), WebSockets (ws://), HTTP REST.
## 🧪 Running Tests
🔬 Hardware Unit Testing:
- Run tests/test_key_timing.ino to verify contact debouncing (<15ms).
- 🌐 Web Audio & Mapping Tests:

```bash
  npm test
```
Validates Morse lookup map coverage for all letters A-Z, numbers 0-9, and punctuations.

📡 MQTT Ping Test:

```bash
  mosquitto_sub -h broker.emqx.io -t iot/morse/decoded
```
## Demo
https://youtu.be/w-XwWIdNpXE?si=ZyVHYn02ufMtoKST
## 💡 Usage / Examples

🆘 Transmitting SOS:

- Press key 3 short bursts ... (letter S).
- Pause 3 units.
- Press key 3 long bursts --- (letter O).
- Pause 3 units.
- Press key 3 short bursts ... (letter S).
- Decoded Output: SOS appears on OLED and web dashboard.
- 💡 Optical Flashlight Mode:
- Aim a standard laser or flashlight beam at the LDR photodiode; pulses will decode without physical wiring.
## 🏢 Used By

🏫 University IoT Laboratories: Practical demonstrations of edge timing and interrupt handling.

📻 Ham Radio Training Clubs: Morse code rhythm training and CW verification.

🚨 Emergency Communication Workshops: Visual light-based signaling setups.

## 👥 Authors
Team Name: Infinite Loopers

Institution: Academy of Technology (AOT)

Ideathon Theme: Morse Code Decoder

    🧑‍💻 Rajesh Mondal — BCL-AOT-0109 • Academy of Technology
    👨‍💻 Team Member 2 - BCL-AOT-0110 • Academy of Technology
    🧑‍💻 Team Member 3 - BCL-AOT-0111 • Academy of Technology
    🧑‍💻 Team Member 4 - BCL-AOT-0112 • Academy of Technology


[@Rajesh_Mondal](https://www.github.com/rajisdevil)
## 🚀 About Me
I'm a full stack developer...


# Hi, I'm Rajesh! 👋


## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://rajesh-portfolio-silk.vercel.app/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rajeshtechie)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)


## Other Common Github Profile Sections
👩‍💻 I'm currently working on developing TollGate, an autonomous machine-to-machine payment protocol built on HTTP 402 for AI agents and IoT sensors, alongside ESP32-based hardware telemetry displays.

🧠 I'm currently learning advanced embedded systems firmware optimization, secure cryptographic voucher verification, and real-time serial communication protocols.

👯‍♀️ I'm looking to collaborate on open-source AI agent tooling, autonomous M2M payment rails, and physical computing/microcontroller prototyping projects.

🤔 I'm looking for help with scaling low-fee stablecoin batch-settlement architectures and building robust TypeScript/Python SDK wrappers for agent wallets.

💬 Ask me about working with ESP32-S3 boards, Arduino prototyping, SSD1306 OLED interfaces, Processing GUI data visualizers, and HTTP 402 machine commerce architecture.

📫 How to reach me reach out via email at rajesh.mondal.25@aot.edu.in or connect through Team CtrlC_CtrlV!

😄 Pronouns: He/Him

⚡️ Fun fact: I love combining physical hardware sensors with custom software interfaces, and when I'm away from the IDE, you can usually find me out riding my commuter motorcycle.


## 🛠 Skills
Javascript, HTML, CSS...


## Badges

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)


## ❓ FAQ

#### Question 1: How does the system distinguish between a dot and a dash?

Answer: ⏱️ It measures the signal duration; an active state lasting ‭$1\times\text{unit}$‬‭‬ (default ~120 ms) is registered as a dot (.), while anything ‭$\ge 3\times\text{units}$‬‭‬ is registered as a dash (-).


#### Question 2: Can the system decode Morse code from a light source instead of a button?

Answer: TollGate uses Batched Settlement. Individual calls are verified off-chain in millisec🔦 Yes, by connecting an LDR or photodiode sensor to the analog/digital input pin, it decodes visual pulses from laser pointers or flashlights.

#### Question 3: Does the decoder require an active internet connection to function?

Answer: 📴 No, core signal decoding and OLED rendering occur completely offline on the edge microcontroller; internet access is only needed for MQTT/WebSocket cloud transmission.

#### Question 4: How do I adjust the decoding speed for faster or slower operators?

Answer: 🎛️ You can modify the BASE_UNIT_MS value in config.h or dynamically publish a new WPM rate to the iot/morse/config MQTT topic.

#### Question 5:  What causes random or duplicate characters during keying?

Answer: 🛑 Mechanical switch bounce; ensure software debouncing (15–20 ms) is enabled in firmware or attach a 100 nF capacitor across the switch terminals.

#### Question 3: Why is the ESP32 failing to connect to the Wi-Fi network?

Answer: 📶 The ESP32 and ESP8266 only support 2.4 GHz Wi-Fi bands; verify your router is not broadcasting solely on 5 GHz.

#### Question 4: Can I use an Arduino Uno instead of an ESP32/ESP8266?

Answer: 🔌 Yes for local buzzer and OLED decoding, but you will need an external network shield (e.g., Ethernet or ESP-01) for MQTT telemetry and web connectivity.

#### Question 5:   How do I fix the OLED screen showing a blank or corrupted display?

Answer: 🔍 Verify that the I2C wiring matches the SDA/SCL pins and confirm that the I2C address is correctly set to 0x3C (or 0x3D) in the firmware setup.
## 💬 Feedback

If you have any feedback, questions from the judging panel, or partnership inquiries regarding GPU/data marketplace pilots, please reach out to:
✉️ Email: rajesh.mondal.25@aot.edu.in (Rajesh Mondal — Team Infinte Loopers)

🐛 GitHub Issues: Open an issue in this repository for bug reports or protocol proposals.
