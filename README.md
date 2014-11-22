3DS Homebrew tutorial
=====================

Introduction
------------

This document explains how to make your own homebrew softwares on Nintendo 3DS / 2DS / new 3DS.
It's in the public domain and all contributions / translations are welcome!
All credits go to [Smealum](http://smealum.net) for his [Ninjhax release](http://smealum.net/ninjhax).

Setup
-----

**Hardware**

Here's what you need to buy to get started:
- A Nintendo 3DS / 2DS console with a firmware version between 4.0.0-7 and 9.2.0-20, or a New3DS with a firmware between 9.0.0-20 and 9.2.0-20. (you can find your firmware version in the "Console parameters" app, on the upper screen.)
- A SD card + a SD card reader.
- A copy of the 3DS game **Cubic Ninja** (new or used)

**Software**

Here's what you need to download and install:
- The latest version of [DevKitPro](http://devkitpro.org). During setup, you can choose to install devkitARM only.
- [ctrulib](https://github.com/smealum/ctrulib/archive/master.zip). Unzip this inside DevKitPro's install folder.
- [Ninjhack's homebrew starter kit](http://smealum.net/ninjhax/dl/starter.zip). Unzip this at the root of your SD card and place the SD card in your console.
- A C++ compatible IDE like [Netbeans](https://netbeans.org/downloads), or a code editor, like [notepad++](http://notepad-plus-plus.org).
- A FTP client like [FileZilla](https://filezilla-project.org) or [WinSCP](http://winscp.net) to upload homebrews directly on your 3DS using wi-fi connection. (optional)
- Latest version of [Python 3.x.x](https://www.python.org), to use advanced features in your homebrews. (optional)

**Homebrew launcher setup**

Follow these steps to install the homebrew launcher on your 3DS (this needs to be done only once):
- Go on Ninjhax's website and [generate the QR code corresponding to your console's firmware](http://smealum.net/ninjhax/#qrcode).
- Enable your 3DS's wi-fi connexion.
- Start the game Cubic Ninja, choose "Create", then "QR code", and finally "Scan QR code". 
- Scan the QR Code, then follow on-screen instructions to start HB launcher.

The next times you turn your console on, just launch Cubic Ninja, choose "Create", then "QR code" and the HB launcher will start directly.

<img src="http://img.ctrlv.in/img/14/11/22/54709c512ae72.png" width=400>

**Homebrew installation**

Two files are needed for a 3DS homebrew to be playable with Ninjhack: a *.3dsx file and a *.smdh file.

If you want to play homebrews on your console, or test your own builds easily, you can use your computer to place them in the "3ds" folder of your SD card.

Note: you can create subfolders in your 3ds folder to organize your homebrews.

You can also upload them directly using wi-fi:
- Start HB launcher.
- Start ftPONY.
- Note the IP and port displayed on the upper screen (for example: "IP: 192.168.0.128 port 5000")
- Start a FTP client on your desktop, and use these credentials to get connected.
- If asked, choose "anonymous connection".
- You should now see your SD card's filesystem and be able to drag & drop files and folders in the "3ds" folder of your SD card.
- Press B to quit ftPONY and launch your new apps.

<img src="http://img.ctrlv.in/img/14/11/22/54709afe2f047.png" width=700>




Anatomy of a homebrew project
==

Let's take a look at our template default, in ctrulib/template. It's a minimal project that does nothing else than printing a white pixel on the upper screen.

It contains:
- a **source** folder, containing a **main.c** file. (this contains the source code of your homebrew)
- a **makefile** file (this contains the instructions to build our homebrew for the HB Launcher)

Let's see how bigger projects are made, for example [Yeti3DS](https://github.com/smealum/yeti3DS). You can notice a few other things:
- an **icon.png** file (This is a 48x48px image displayed on HB launcher alongside your homebrew. Optional but preferable.) 
- the **source** folder contains more **xxx.c** files and **xxx.h** files. (this is a common way to structure and organize a C/C++ project. Note that the main function ````int main()```` remains in **main.c**, the other C files are used to store additional code and data).

In many projects, like [3dscraft](https://github.com/smealum/3dscraft) you can find a **data** folder containing **xxx.bin** files. Those are images, and we'll explain later how to make and how to use them.

Build procedure
--

Let's go back to our ctrulib/template folder.
- Open a CLI (command line invite). If you're on Windows, press Shift + right click on the template folder and choose "Open a CLI here".
- type ````make```` and press enter.
- After a few seconds, the process finishes and you can find a build folder (you can ignore it) and two new files **.3dsx** and **.smdh**. You can send them on your SD card to test the homebrew on real hardware.
- You can rebuild those files anytyme after editing your source code.

New project
--

Make a copy of the template folder, place it where you want, and name it "tuto". 

Homebrew development
==

coming soon!
