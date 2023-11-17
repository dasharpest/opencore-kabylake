## 🌿 Information
OpenCore configs for installing macOS on both Intel KabyLake based desktops & ThinkPad E560 series laptops.

[![macOS](https://img.shields.io/badge/macOS-Monterey-blue)](https://developer.apple.com/documentation/macos-release-notes)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.9.3-green)](https://github.com/acidanthera/OpenCorePkg)

## 💾 Installation
A guide to create the USB installer with the contained EFI folders can be found [here](https://dortania.github.io/OpenCore-Install-Guide/installer-guide) and also steps to configure a dual / multi-boot system [here](dualboot-guide.md).

## 💻 Bios settings

| Menu     |                   |                                 | Setting     |
|----------|-------------------|---------------------------------|-------------|
| Config   | USB               | UEFI BIOS Support               | `Enable `   |
|          | Power             | Intel SpeedStep Technology      | `Enable `   |
|          |                   | CPU Power Management            | `Enable `   |
|          | CPU               | Hyper-Threading Technology      | `Enable `   |
| Security | Security Chip     |                                 | `Disable `  |
|          | Memory Protection | Execution Prevention            | `Enable `   |
|          | Virtualization    | Intel Virtualization Technology | `Enable `   |
|          |                   | Intel VT-d Feature              | `Enable `   |
|          | Anti-Theft        | Computrace                      | `Disable `  |
|          | Secure Boot       |                                 | `Disable `  |
|          | Intel SGX         |                                 | `Disable `  |
|          | Device Guard      |                                 | `Disable `  |
| Startup  | UEFI/Legacy Boot  |                                 | `UEFI Only` |
|          | CSM Support       |                                 | `No`        |
|          | Boot Mode         |                                 | `Quick`     |

## 🎉 Credits
[acidanthera](https://github.com/acidanthera), [dortania](https://github.com/dortania), [luchina-gabriel](https://github.com/luchina-gabriel/BASE-EFI-INTEL-DESKTOP-7THGEN-KABY-LAKE), [rsdev69](https://github.com/rsdev69/ThinkPad-E560-Hackintosh), [TheHowToGuy123](https://www.youtube.com/watch?v=163V9Q6X4uM), [Brandon Yen](https://www.youtube.com/watch?v=ztxHRGdX0Sw.)
