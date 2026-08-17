# Dell-latitude-5300-2-in-1-MacOS-Tahoe

Dell Latitude 5300 (2-in-1) - macOS Tahoe Hackintosh
This repository contains the OpenCore EFI folder to successfully boot macOS 26 Tahoe on the Dell Latitude 5300 2-in-1.

💻 Hardware Specifications
Component	Specification
Model	Dell Latitude 5300 2-in-1
CPU	Intel Core i5 / i7 (Whiskey Lake)
GPU	Intel UHD Graphics 620
RAM 16gb DDR4 2400
Storage SK Hynix 512gb
Wi-Fi / BT	Intel Wireless AC 9560
Audio	Realtek ALC236 (ALC256)
Bootloader	OpenCore [Enter your version here, e.g., 1.0.1]
macOS	macOS Sequoia (15.x)
✅ What Works
 Intel UHD Graphics 620 (Full QE/CI Hardware Acceleration)
 Internal Display (with brightness control)
 Wi-Fi & Bluetooth (via itlwm / IntelBluetoothFirmware)
 Audio (Internal Speakers & Headphone Jack)
 Touchpad & Keyboard
 USB Ports
 Battery Readout
 Sleep / Wake
 App Store & iCloud
 External Displays (via USB-C / WD19 Dock)
❌ What Doesn't Work
AirDrop, Handoff, Continuity: Intel Wi-Fi cards do not support Apple's AWDL protocol. (Requires physically swapping the Wi-Fi card to a Broadcom BCM94360NG).
Fingerprint Scanner: macOS does not support third-party biometric sensors. The Broadcom ControlVault 3 sensor is completely incompatible.
Face ID / IR Camera: Not supported by macOS.
iMessage / FaceTime: Apple's servers may temporarily flag new Hackintosh accounts. You may need to call Apple Support to whitelist your Apple ID.
⚠️ Important Note Before Using!
DO NOT use the config.plist exactly as it is without changing the SMBIOS!

Before copying this EFI to your USB drive, you MUST generate your own unique Mac Serial Number, MLB, and UUID using GenSMBIOS. The SMBIOS used in this build is MacBookPro15,2.

If you use my exact Serial Number, both of our Apple IDs will get banned by Apple!

🚀 Installation / Usage
Create a macOS Sequoia bootable USB.
Download this repository.
Open EFI/OC/config.plist with ProperTree or PlistEdit Pro.
Generate a new MacBookPro15,2 SMBIOS and paste the values into the PlatformInfo -> Generic section.
Save the file.
Copy the entire EFI folder to the hidden EFI partition of your bootable USB.
Boot from the USB and install macOS!
Custom Boot Arguments Used:
revpatch=sbvmm (Required to spoof the hardware model for macOS Sequoia App Store updates)
agdpmod=vit9696 & -igfxcdc (Required for external monitor/dock support)
🤝 Credits
Dortania for the incredible OpenCore guide.
The Hackintosh Community.
