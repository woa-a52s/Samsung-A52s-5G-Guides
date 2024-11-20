

# Status of Samsung Galaxy A52s 5G

The development for the Windows Port is currently scheduled as follows:

- ~~Milestone #0: Early UEFI/OS bring up, proof of concept~~ Completed!
- Milestone #1: SoC hardware bringup in Windows OS, end goal is to have all hardware blocks/components of the SoC in a functional or communicating state by the end of the milestone, but not have it interface with the OS if it isn't already done. **In progress!**
- Milestone #2: Bug fixes, this is where we will fix major issues like crashes, etc
- Milestone #3: Calibration/Tuning, calibrate everything to work as it should be.
- Milestone #4: To be defined?

_No ETA will be provided for **any** of these development phases_

---

Global progress: 43.47%

| Feature                | Description                                                                                                    | Working state |
|------------------------|----------------------------------------------------------------------------------------------------------------|---------------|
| ⌨️ Side buttons        |                                                                                                                | ✅             |
| ♋ Cellular Calls       | MPSS is not functional                                                                                         | ❌             |
| ♋ Cellular Data        | MPSS is not functional                                                                                         | ❌             |
| ♋ Cellular Texts       | MPSS is not functional                                                                                         | ❌           |
| ♋ WiFi                 |                                                                                                                | ✅           |
| 🌡️ Thermal sensors      |                                                                                                                | ✅           |
| 🎆 GPU                  |                                                                                                                | ❌           |
| 👆 Touchscreen          |                                                                                                                | ✅           |
| 💤 Modern Standby       |                                                                                                                | ✅           |
| 📌 GPS                  |                                                                                                                | ✅           |
| 📦 UFS                 |                                                                                                                | ✅           |
| 📲 Display              |                                                                                                                | ✅           |
| 📳 Vibration motor      |                                                                                                                | ❌           |
| 📸 [Camera Flash](https://gist.github.com/gus33000/8720db998a7ab9c164bd6a96e00dac32) | ICP is not functional                             | ❌           |
| 🔋 Battery              | A52s uses custom PMIC, fuelgauge driver needs to be written                                                    | ❌           |
| 🔌 Charger              | Charging is not over ADSP, needs custom implementation                                                         | ❌           |
| 🔵 Bluetooth            |                                                                                                                | ✅           |
| 🧭 Sensors              |                                                                                                                | ❌           |
| 🧮 SoC Cores            |                                                                                                                | ✅           |
| 🪵 USB C               | Requires power delivery                                                                                        | ⚠️           |
| 📸 Camera Sensor        | ICP is not functional                                                                                          | ❌           |
| 🔊 Audio               |                                                                                                                | ❌           |
| 🧬 Fingerprint scanner  |                                                                                                                | ❌           |

