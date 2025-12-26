# 🍎 Hackintosh AMD EDITION EFI – ASUS TUF A17

OpenCore EFI for running macOS on **ASUS TUF A17(FA706IH)**  
Tested on **AMD Ryzen 5 4600H** with **Radeon iGPU (NootedRed)**.

> ⚠️ This EFI is hardware-specific. Use it as a **reference**, not blindly.

---

## 🚀 macOS Compatibility

| macOS Version | Status |
|-------------|--------|
| Monterey (12.x) | ✅ Stable |
| Ventura (13.x) | 🟡 On-going |

---

## 🖥️ Hardware Specs

| Component | Details |
|---------|--------|
| Model | ASUS TUF A15 |
| CPU | AMD Ryzen 5 4600H |
| iGPU | AMD Radeon (NootedRed) |
| dGPU | GTX 1650 ❌ (Disabled) |
| RAM | 16GB DDR4 |
| Storage | NVMe SSD |
| Audio | Realtek ALC256 (AppleALC) |
| Ethernet | Realtek RTL8111 |
| Wi-Fi / BT | Realtek 8822CE ❌ |
| SMBIOS | MacBookPro16,3 |

---

## ✅ What Works

- ✔ macOS boot & install
- ✔ Hardware acceleration (AMD iGPU)
- ✔ Audio (AppleALC)
- ✔ Ethernet
- ✔ USB ports
- ✔ Sleep / Wake
- ✔ Brightness control
- ✔ iServices (with proper SMBIOS)

---

## ❌ What Doesn’t Work

- ❌ NVIDIA GTX 1650 (no macOS support)
- ❌ Sidecar / Universal Control

---

## 🧩 ACPI Patches & SSDTs

Included SSDTs:

- `SSDT-EC` – Embedded Controller
- `SSDT-PLUG-ALT` – CPU power management (AMD)
- `SSDT-PNLF` – Backlight control
- `SSDT-USBX` – USB power properties
- `SSDT-USB-Reset` – USB stability
- `SSDT-XOSI` – OSI handling
- `SSDT-ALSO` – Audio support
- `SSDT-Disable_GPU_GPP0` – Disable NVIDIA dGPU
- `SSDT-Disable_Network_GPP4` – Disable unused PCI device

---

## 🖥️ Graphics Notes (NootedRed)

- Uses **NootedRed** for AMD iGPU acceleration
- If internal display is black:
  - Try newer NootedRed build
  - Increase VRAM via **Smokeless UMAF**
  - Use `-NRedDPDelay` boot-arg

---

## ⚠️ Known Issues

- Installer may stall near final minutes if NVRAM routing is wrong
- Some BIOS versions require manual dGPU disable

---

## 📂 EFI Structure

```bash
EFI
├── BOOT
└── OC
├── ACPI
├── Drivers
├── Kexts
├── Resources
└── config.plist
```

---

## 🙌 Credits

- **Acidanthera** – OpenCore, Lilu, AppleALC
- **Dortania** – Documentation
- **NootedRed** – AMD iGPU patches
- Hackintosh community 🖤

---

## ⚠️ Disclaimer

This project is provided **as-is**.  
I am **not responsible** for data loss, hardware damage, or failed installs.  
Proceed only if you know what you’re doing.
