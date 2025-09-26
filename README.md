# Arduino-Script
A simple arduino script 
# USB-HID

**Purpose:** Educational, benign demonstration of Arduino USB-HID (keyboard) behavior for defensive research and learning.

This repository contains a single **sanitized** Arduino sketch () that demonstrates how an Arduino-compatible board that exposes a USB keyboard (HID) can send keystrokes to a host. The demo *only* opens Notepad and types a harmless message — it does **not** attempt to disable security software, escalate privileges, or capture user input.

> **Important:** Only run this on machines you own or on which you have explicit permission to test. Prefer an isolated test machine or VM.

## What the demo does
1. Waits for USB enumeration.
2. Opens the Windows Run dialog (Win+R).
3. Types `notepad` and presses Enter to open Notepad.
4. Types a friendly test message into Notepad.
5. Stops sending keystrokes (one-shot behavior).

This demonstrates timing, key sequences, and how HID keyboard automation behaves without doing anything harmful.

## Files
- `sanitized_notepad_demo.ino` — the Arduino sketch (safe demo).
- `README.md` — this file.

## Requirements
- Arduino IDE (or `arduino-cli`) installed.
- An Arduino-compatible board that supports USB HID (e.g., Arduino Leonardo, Micro, Pro Micro).
- USB cable and an isolated test machine (recommended).

## How to build and upload (sanitized demo)
1. Open Arduino IDE.
2. Create a new sketch and paste the contents of `sanitized_notepad_demo.ino`.
3. Select the correct **Board** (e.g., `Arduino Leonardo`) and **Port** under Tools.
4. Click **Verify** to compile.
5. Click **Upload** to flash the board.
6. On the test machine, **do not** have any sensitive documents open. You can open an empty Notepad or simply allow the demo to open it for you.
7. After upload, re-plug the board into the test machine (or press the board reset if needed). The demo will run once and type into the foreground window (or open Notepad to receive typed text).

## Safe testing checklist
- Use a non-production machine or an isolated VM (with USB passthrough).
- Take a snapshot or backup before testing.
- Disconnect from the network if you want maximum isolation.
- Do not run on other people’s machines without written consent.

## Troubleshooting
- If Notepad does not open: ensure the board enumerates as a keyboard and that the host allows HID input.
- If the message appears in the wrong place: ensure no other window has focus when the demo runs.
- If timings fail (e.g., notepad typed before Run dialog opens), increase `delay()` values in the sketch to allow slower hosts to respond.

## License & Usage
This repository is intended for educational and defensive purposes. Do not use it to perform unauthorized testing. By using this repository you agree to follow all applicable laws and to obtain explicit authorization before testing on systems you do not own.

## Liability & Disclaimer ##

**No warranty.** The code and documentation in this repository are provided "as is", without warranty of any kind, express or implied. The maintainers and contributors make no representations or warranties about the suitability, reliability, safety, or legality of the content for any purpose.

**No responsibility.** By using this repository you accept full responsibility for your actions. The repository owners, contributors, and maintainers are **not** responsible

