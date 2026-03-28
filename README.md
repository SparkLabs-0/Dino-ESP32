# 🦕 Dino ESP32

A T-Rex style endless runner game running on an **ESP32** with a tiny OLED display and a buzzer — because why play Chrome's dinosaur game when you can build your own?

---

## 📸 Demo
[Dino ESP32 running](assets/Screencast from 2026-03-28 22-53-02.gif)

---

## 🎮 How to Play

- **Press the button** on the start screen to begin
- **Press again** while running to jump over cacti
- **Don't get hit** — the game ends on collision
- Your score goes up over time, faster = harder
- A little beep plays every 100 points 🎵

---

## 🧰 Hardware Required

| Component          | Details                      |
|--------------------|------------------------------|
| Microcontroller    | Any ESP32 board              |
| Display            | SSD1306 OLED 128x64 (I2C)   |
| Button             | Momentary push button        |
| Buzzer             | Passive buzzer               |
| Wires + Breadboard | The usual                    |

> This was built and designed on an **ESP32-C3** — it's tiny, fits perfectly on a small breadboard, and is cheap. Any ESP32 variant should work fine though, just double check your I2C and GPIO pins.

---

## 🔌 Wiring

The pin numbers below are for the **ESP32-C3**. Adjust them to match your board if you're using a different variant.

| ESP32-C3 Pin | Connected To              |
|--------------|---------------------------|
| GPIO 5       | Button (other leg → GND)  |
| GPIO 10      | Buzzer +                  |
| GND          | Buzzer − / Button GND     |
| GPIO 8 (SDA) | OLED SDA                  |
| GPIO 9 (SCL) | OLED SCL                  |
| 3.3V         | OLED VCC                  |
| GND          | OLED GND                  |

> ⚠️ The OLED runs on **3.3V**, not 5V. Double check before powering on.

---

## 🛠️ Software & Libraries

Install these via the Arduino Library Manager before flashing:

- [U8g2](https://github.com/olikraus/u8g2) — OLED display driver
- Wire (built-in) — I2C communication

Board package needed: **ESP32 by Espressif** — install via Arduino Boards Manager.

---

## 🚀 Getting Started

1. Clone this repo
   ```bash
   git clone https://github.com/yourusername/dino-esp32.git
   ```
2. Open `dino_game.ino` in Arduino IDE
3. Select your ESP32 board
4. Wire everything up according to the table above
5. Hit upload and press the button!

---

## ⚙️ Configuration

At the top of `dino_game.ino` you can easily tweak:

```cpp
#define JUMP_HEIGHT  40   // higher = dino goes higher
#define JUMP_SPEED   4    // lower = floatier jump
#define GROUND_Y     60   // ground line Y position
#define DINO_BASE_Y  38   // dino's resting Y position
```

---

## 📁 Project Structure

```
dino-esp32/
├── dino_game.ino   # main sketch
└── README.md       # you are here
```

---

## 🙌 Credits

- Original game concept by **Ishani & Arijit Sengupta** (30DLIS kit)
- ESP32 port, ground detail, jump physics, and buzzer rework by **you**
- Inspired by the Chrome dinosaur game 🦕

---

## 📄 License

MIT License — do whatever you want with it, just keep the credits. See `LICENSE` for details.
