
```
███████╗██████╗ ███████╗███████╗     ██████╗ ██████╗ ███████╗███████╗ ██████╗
██╔════╝██╔══██╗██╔════╝██╔════╝    ██╔═══██╗██╔══██╗██╔════╝██╔════╝██╔════╝
█████╗  ██████╔╝█████╗  █████╗      ██║   ██║██████╔╝███████╗█████╗  ██║     
██╔══╝  ██╔══██╗██╔══╝  ██╔══╝      ██║   ██║██╔═══╝ ╚════██║██╔══╝  ██║     
██║     ██║  ██║███████╗███████╗    ╚██████╔╝██║     ███████║███████╗╚██████╗
╚═╝     ╚═╝  ╚═╝╚══════╝╚══════╝     ╚═════╝ ╚═╝     ╚══════╝╚══════╝ ╚═════╝
              from https://t.me/ventalgroup
```

**Free Opsec** is a command-line utility that provides a one-command installation for a curated suite of privacy and security tools on Debian-based Linux distributions. It features a unique, animated terminal interface and is designed to be simple, fast, and effective.

## Features

- **One-Command Install**: A single `apt install` command to get a full suite of security tools.
- **Animated Interface**: A visually engaging installation process with a running cat animation and live progress tracking.
- **Curated Software**: A selection of essential, free, and privacy-focused applications.
- **Wide Compatibility**: Works on Kali Linux, Pop!_OS, Ubuntu, and other Debian-based systems.

## Included Software

The installer will automatically set up the following applications:

| Category          | Software        |
|-------------------|-----------------|
| **Web Browser**   | Brave Browser   |
| **Anonymity**     | Tor Browser     |
| **VPN**           | Proton VPN      |
| **Messaging**     | Signal, Telegram|
| **Password Manager**| KeePassXC       |
| **System Cleaner**| BleachBit       |

## Installation

Getting started is simple. Just clone the repository and run the setup script.

# Quick safety net: fix any leftover mess
sudo killall apt apt-get 2>/dev/null || true
sudo rm -f /var/lib/dpkg/lock* /var/cache/apt/archives/lock /var/lib/apt/lists/lock
sudo dpkg --configure -a
sudo apt install -f
sudo apt update

# Make script ready + run it (this does the heavy lifting: compiles cat binary, adds repo if needed, etc.)
chmod +x setup.sh
sudo ./setup.sh

# Final install step
sudo apt update
sudo apt install opsec -y

# Optional: reconfigure if it whines about post-install
sudo dpkg-reconfigure opsec || true

That's it! The animated installer will launch and configure everything for you.

## How It Works

The `opsec` package uses a compiled C++ binary to display the permanent ASCII watermark and the 20-frame cat animation. This binary then executes a background script to handle the installation of the software suite, providing a seamless and branded experience.

join https://t.me/ventalgroup
