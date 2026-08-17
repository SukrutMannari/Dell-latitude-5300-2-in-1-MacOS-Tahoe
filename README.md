# Dell-latitude-5300-2-in-1-MacOS-Tahoe

# Dell-latitude-5300-2-in-1-MacOS-Tahoe

This repository contains the OpenCore EFI folder to successfully boot **macOS 26 Tahoe** on the Dell Latitude 5300 2-in-1.

## 💻 Hardware Specifications

| Component | Specification |
| --- | --- |
| **Model** | Dell Latitude 5300 2-in-1 |
| **CPU** | Intel Core i5 / i7 (Whiskey Lake) |
| **GPU** | Intel UHD Graphics 620 |
| **RAM** | 16GB DDR4 2400MHz |
| **Storage** | SK Hynix 512GB SSD |
| **Wi-Fi / BT** | Intel Wireless AC 9560 |
| **Audio** | Realtek ALC236 (ALC256) |
| **Bootloader** | OpenCore |
| **macOS** | macOS 26 (Tahoe) |

---

## ✅ What Works
- [x] Intel UHD Graphics 620 (Full QE/CI Hardware Acceleration)
- [x] Internal Display (with brightness control)
- [x] Wi-Fi & Bluetooth (via `itlwm` / `IntelBluetoothFirmware`)
- [x] Audio (Internal Speakers & Headphone Jack)
- [x] FaceTime (Webcam & Microphone)
- [x] Touchpad & Keyboard
- [x] USB Ports
- [x] Battery Readout
- [x] Sleep / Wake
- [x] App Store & iCloud
- [x] External Displays (via USB-C / WD19 Dock)

## ❌ What Doesn't Work
- **AirDrop, Handoff, Continuity:** Intel Wi-Fi cards do not support Apple's AWDL protocol. (Requires physically swapping the Wi-Fi card to a Broadcom BCM94360NG).
- **Fingerprint Scanner:** macOS does not support third-party biometric sensors. The Broadcom ControlVault 3 sensor is completely incompatible.
- **Face ID / IR Camera:** Not supported by macOS.
- **iMessage:** Apple's servers may temporarily flag new Hackintosh accounts. You may need to call Apple Support to whitelist your Apple ID.

---

## ⚠️ Important Note Before Using!
**DO NOT use the `config.plist` exactly as it is without changing the SMBIOS!**

Before copying this EFI to your USB drive, you **MUST** generate your own unique Mac Serial Number, MLB, and UUID using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS). 
The SMBIOS used in this build is **`MacBookPro15,2`**.

If you use my exact Serial Number, both of our Apple IDs will get banned by Apple!

---

## 🚀 Installation / Usage

1. Create a macOS Tahoe bootable USB.
2. Download this repository.
3. Open `EFI/OC/config.plist` with [ProperTree](https://github.com/corpnewt/ProperTree) or PlistEdit Pro.
4. Generate a new `MacBookPro15,2` SMBIOS and paste the values into the `PlatformInfo -> Generic` section.
5. Save the file.
6. Copy the entire `EFI` folder to the hidden EFI partition of your bootable USB.
7. Boot from the USB and install macOS!

### Custom Boot Arguments Used:
- `revpatch=sbvmm` (Required to spoof the hardware model for macOS Tahoe App Store updates)
- `agdpmod=vit9696` & `-igfxcdc` (Required for external monitor/dock support)

## 🤝 Credits
- [Dortania](https://dortania.github.io/OpenCore-Install-Guide/) for the incredible OpenCore guide.
- The Hackintosh Community.
