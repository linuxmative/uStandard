
# 🧱 uStandard — Custom Ubuntu-Based Live ISO Builder

`uStandard` is a script for creating a **customizable Live ISO** based on Ubuntu. It provides a minimal yet fully usable system with drivers, X11, Wi-Fi, multimedia, auto-login, and the ability to install any desktop environment (GNOME, KDE, XFCE, etc.).

This project builds upon the foundation of [uMini](https://github.com/linuxmative/umini), offering a more complete and installation-ready system with all essential components included.

----------

## 🚀 Features

-   📏 Build a fully functional **Live ISO** from Ubuntu base
    
-   ⚙️ Uses `debootstrap` to create a minimal root filesystem
    
-   🤊 SquashFS (XZ compressed) and hybrid ISO with GRUB (BIOS + UEFI support)
    
-   🛁 Includes drivers and support for:
    
    -   Ethernet & Wi-Fi (via `systemd-networkd` and `iwd`)
        
    -   Audio (ALSA + PulseAudio)
        
    -   Graphics (Intel, AMD, Radeon) with X11/Mesa
        
    -   Printing (CUPS)
        
    -   Multimedia codecs (GStreamer, libav)
        
-   ❌ Snap and Ubuntu Pro packages are **blocked and purged**
    
-   👤 Predefined users:
    
    -   `ustandard:ustandard` — auto-login
        
    -   `ubuntu:ubuntu`
        
    -   `root:toor`
        
-   🕒 Timezone auto-detected from host
    
-   🪄 System cleanup & compression included
    

----------

## 📆 Software Stack

The script builds a minimal but install-ready system with:

-   Linux kernel, firmware & headers
    
-   Base system tools (network, disk, input/output utilities)
    
-   Full live boot support via `casper`
    
-   Core system services (systemd, udev, dbus)
    
-   Fonts, codecs, printing support
    
-   X11 and graphics stack
    
-   No graphical desktop environment by default (headless or DE-ready)
    

----------

## ⚖️ How to Use

```bash
git clone https://github.com/linuxmative/uStandard.git
cd uStandard
chmod +x ustandard.sh
./ustandard.sh

```

The script will:

1.  Install all required build dependencies
    
2.  Bootstrap a minimal system into a chroot
    
3.  Configure and harden the system
    
4.  Generate kernel/initrd, squashfs, and GRUB bootloader
    
5.  Produce a hybrid ISO image: `uStandard-noble-YYYYMMDD.iso`

----------

## 📦 Download Prebuilt ISO

A prebuilt ISO is available under the [Releases section](https://github.com/linuxmative/uStandard/releases).  
You can test the live image on real hardware or in a virtual machine (e.g., VirtualBox or QEMU).    

----------

## 🦪 Test the ISO

```bash
qemu-system-x86_64 -m 2048 -cdrom uStandard-noble-YYYYMMDD.iso

```

----------

## 💡 Extend the System

Once booted, install your preferred desktop environment:

```bash
sudo apt update
sudo apt install xfce4 lxdm

```

Other options: GNOME, KDE, Cinnamon, MATE, LXDE, LXQt, etc.

----------

## ☕ Support the Project

If you find **uStandard** helpful, please consider [donating via PayPal](https://www.paypal.com/donate/?hosted_button_id=8P43MJQ2TM7S2) to help keep the project alive.

Your support encourages further development, better documentation, and more features.  
Even a small donation goes a long way in supporting open-source software made for the community.

----------

## ⚖️ License

This project is licensed under the **MIT License**.  
See `LICENSE` for details.

----------

## 💼 Disclaimer

This project is **not affiliated with Ubuntu, Canonical Ltd., or any of their trademarks**.  
Ubuntu is a registered trademark of Canonical Ltd.  
All trademarks are property of their respective owners.

The uStandard project uses **Ubuntu base packages** to build a custom system, but it does **not use any proprietary software or branding** from Canonical.  
This project is intended for **educational and personal use**, and all automated steps are transparent and reproducible.

----------

## 📬 Author

**Maksym Titenko** [@titenko](https://github.com/titenko)  
GitHub: [@linuxmative](https://github.com/linuxmative)  
Website: [linuxmative.github.io](https://linuxmative.github.io)
