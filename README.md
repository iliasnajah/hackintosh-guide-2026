```markdown
# Hackintosh-Guide-2026

**Simple, up-to-date OpenCore Hackintosh guide (2026)**  
A curated collection of links, commands, and recommended tools to build a Hackintosh from Windows. This repo is a *how-to reference* — read everything before you start.

> ⚠️ **Legal / safety note:** Installing macOS on non-Apple hardware may violate Apple's EULA. This guide is educational. Proceed at your own risk.

---

## Table of Contents

* [Overview](#overview)
* [Prerequisites](#prerequisites)
* [Repo layout](#repo-layout)
* [Important Links](#important-links)
* [Step-by-step Summary](#step-by-step-summary)
* [Common Commands](#common-commands)
* [Post-install Tips](#post-install-tips)
* [Troubleshooting & Help](#troubleshooting--help)
* [Contributing](#contributing)
* [License](#license)

---

## Overview

This repository collects the modern workflow (Windows-based) to create a bootable OpenCore macOS installer, prepare an EFI, map USB ports, and do post-install fixes. It uses community tools to simplify the process.  

---

## Prerequisites

* PC/laptop with UEFI (modern systems recommended).  
* USB stick (16GB or larger).  
* Windows 10/11 with admin rights.  
* Python 3 (for macrecovery scripts and USB mapping).  
* Basic familiarity with BIOS/UEFI, disk partitioning, and editing `config.plist`.

---

## Repo layout (suggested)

```

Hackintosh-Guide-2026/
├─ README.md
├─ LICENSE
├─ assets/        <-- screenshots, diagrams
├─ efi-samples/   <-- example EFI structure
├─ scripts/       <-- commands, batch/python scripts
└─ docs/          <-- troubleshooting and notes

````

---

## Important Links

* **OpenCore Install Guide (Dortania)** — https://dortania.github.io/OpenCore-Install-Guide/installer-guide/windows-install.html#downloading-macos  
* **OpCore-Simplify** — https://github.com/lzhoang2801/OpCore-Simplify  
* **USBToolBox (tool)** — https://github.com/USBToolBox/tool  
* **USBToolBox (kext)** — https://github.com/USBToolBox/kext  
* **OCAuxiliaryTools (OCAT)** — https://github.com/ic005k/OCAuxiliaryTools  
* **Rufus** — https://rufus.ie/en/  
* **Community help** — https://www.reddit.com/r/hackintosh/  
* **Video walkthrough (optional)** — user-supplied video link  

---

## Step-by-step Summary

1. **Check hardware & compatibility** — CPU, GPU, Wi-Fi, Bluetooth. Some adapters may be needed.  
2. **Download macOS installer on Windows** — use `macrecovery.py` with Python 3.  
3. **Create USB installer** — format USB and add macOS recovery files, or use Rufus.  
4. **Prepare base OpenCore EFI** — copy `EFI` folder from OpenCorePkg.  
5. **Use OpCore-Simplify** — scaffold your EFI and config.plist.  
6. **Map USB ports** — use USBToolBox to generate a working USB map and kexts.  
7. **Edit `config.plist` and add kexts** — use OCAuxiliaryTools to manage EFI.  
8. **Adjust BIOS/UEFI settings** — disable Secure Boot, enable AHCI, enable UEFI boot.  
9. **Boot from USB and install macOS** — format drive with Disk Utility, then install.  
10. **Post-install fixes** — copy EFI to disk, install missing kexts, test audio, GPU, sleep.

---

## Common Commands (examples)

**Download macOS (Sonoma example):**
```bash
py macrecovery.py -b Mac-226CB3C6A851A671 -m 00000000000000000 download
````

**Rufus USB creation:**
Open Rufus → select USB → `Boot selection: Not bootable` → File system `Large FAT32` → Start → add recovery files.

**USBToolBox mapping:**
Run `USBToolBox/tool` → generate `USBMap.kext` or `USBInjectAll.kext` → add to EFI.

---

## Post-install Tips

* Backup working EFI versions.
* After macOS updates, review kext compatibility and OpenCore versions.
* Use external adapters if internal Wi-Fi/BT is unsupported.
* Refer to subreddit and GitHub issues for model-specific fixes.

---

## Troubleshooting & Help

* Read the troubleshooting section of the [Dortania guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/windows-install.html).
* Community support: [r/hackintosh](https://www.reddit.com/r/hackintosh/).

---

## Contributing

* Add scripts, EFI samples, or post-install fixes.
* Update the guide with new macOS/OpenCore versions.
* Submit pull requests with improvements.

---

## License

This repository is under the **MIT License**. See [LICENSE](LICENSE) file.

```
::contentReference[oaicite:0]{index=0}
```
