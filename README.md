# Potato.ImageFlasher
[![Build Status](https://travis-ci.org/mashed-potatoes/Potato.ImageFlasher.svg?branch=master)](https://travis-ci.org/mashed-potatoes/Potato.ImageFlasher)
[![NuGet Version](https://img.shields.io/nuget/v/Potato.ImageFlasher.svg)](https://www.nuget.org/packages/Potato.ImageFlasher)
[![Nuget](https://img.shields.io/nuget/dt/Potato.ImageFlasher)](https://www.nuget.org/packages/Potato.ImageFlasher)
![GPL-3.0](https://img.shields.io/github/license/mashed-potatoes/Potato.ImageFlasher.svg)

A tiny library for bootloader flashing in VCOM_DOWNLOAD mode on Huawei phones.

Based on [@penn5](https://github.com/penn5)'s project — [hisi-idt](https://github.com/penn5/hisi-idt).

# Example

```c#
var flasher = new ImageFlasher();

// Open serial port, for example COM3
flasher.Open("COM3");

// Write xloader image to 0x00020000
flasher.Write("xloader.img", 0x00020000);

// Write fastboot image to 0x1AC00000 with progress reporting
flasher.Write("fastboot.img", 0x1AC00000, x => Console.WriteLine($"Progress: {x}%"));

// Close serial port
flasher.Close();
```

# License

[GNU General Public License v3.0](LICENSE.txt)
