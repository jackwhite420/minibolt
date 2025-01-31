---
layout: default
title: Operating system
nav_order: 20
parent: System
---
<!-- markdownlint-disable MD014 MD022 MD025 MD033 MD040 -->
{% include include_metatags.md %}

# Operating system

{: .no_toc }

---

We configure the PC and install the Linux operating system.

---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Which operating system to use?

We use Ubuntu Server LTS (Long Term Support) OS, without a graphical user interface.
This provides the best stability for the PC and makes the initial setup a breeze.

Ubuntu Server is based on the [Debian](https://www.debian.org/){:target="_blank"} Linux distribution, which is available for most hardware platforms.
To make this guide as universal as possible, it uses only standard Debian commands.
As a result, it should work smoothly with a personal computer while still being compatible with most other hardware platforms running Debian.

## Balena Etcher and Ubuntu Server

To flash the operating system **.iso** to the pen drive, we will use the [Balena Etcher](https://www.balena.io/etcher/){:target="_blank"} application. Go to the website and download the correct binary accordingly to your OS.

* Direct download Ubuntu Server LTS doing click [here](https://releases.ubuntu.com/22.04.2/ubuntu-22.04.2-live-server-amd64.iso) or going to the official Ubuntu Server [website](https://ubuntu.com/download/server) and clicking on the **"Download Ubuntu Server xx.xx LTS"** button
* **Start** the **Balena Etcher**
* Select **"Flash from file"** --> Select Ubuntu Server LTS **.iso** file previously downloaded

## Write the operating system to the pen drive

* Connect the pen drive to your regular computer
* Click on **"Select target"**
* Select your pen drive unit
* Click on **"Flash!**"

Balena Etcher will now flash the operating system to your drive and validate it.

✔️ It should display a **"Flash Complete!"** message after.

## Start your PC

* **Safely eject** the pen drive from your regular computer
* **Connect to your selected PC** for the MiniBolt node
* **Attach a screen**, a **keyboard** and the **Ethernet** wire of the Internet (not the case for Wifi connection) to the **PC** and start it
* Press the key fastly to **enter to BIOS setup** or directly to the **boot menu** to select the **pen drive as the 1st boot priority device** (normally, F9, Esc, F12, or Supr keys)

   💡 In this step, you might want to take advantage of activating the **"Restore on AC"** or similar in the BIOS setup. Normally found in **Advanced** -> **ACPI Configuration**, switching to **"Power ON"** or similar. With this, you can get the PC to start automatically after a power loss, ensuring services are back available in your absence.

* If you configured boot options in BIOS, **save changes and exit**. This start automatically with the Ubuntu Server guided installation. You will keep selecting **"Try or Install Ubuntu Server"** and press **enter**, or wait 20 seconds for it to start automatically.

## Ubuntu Server installation

Use the **UP**, **Down** and **ENTER** keys of your keyboard to navigate to the options. Follow the next instructions:

**1.** On the first screen, select the language of your choice **(English recommended)**

**2.** If there is an installer update available, select **"Update to the new installer"**, press **enter** and wait

**3.** Select your keyboard layout and variant **(Spanish recommended to Spanish native speakers)** and press **done**

**4.** Keep selecting **"Ubuntu Server"** as the base for the installation, down to **done** and press **enter**

**5.** Select the interface network connection that you choose to use **(Ethernet recommended)** and **take note of your IP** obtained automatically through DHCP. (Normally 192.168.x.xx). Press **done**

**6.** Leave the empty next option if you don't want to use an HTTP proxy to access it. Press **done**

**7.** If you don't want to use an alternative mirror for Ubuntu, leave it empty and press **done** directly

**8.** Configure a **guided storage layout**, with 2 options:

> **8.1.** Check **"Use an entire disk"**, if you have **only one primary unit storage (1+ TB)**. In this case, ensure that you **uncheck "Set up this disk as an LVM group"** before select **done** and press **enter**. Then, continue with **step 9**.

> **8.2.** Check **"Custom storage layout"**, if you want to use one **secondary** disk, e.g. primary for the system and secondary disk for data (blockchain, indexes, etc)(1+ TB). For this case, go to --> [Store data in a secondary disk](../bonus/system/store-data-secondary-disk.md) bonus guide, to get instructions about how to follow, and then continue with **step 10**.

**9.** Confirm destructive action by selecting the **Continue** option. Press **enter**

🚨 **This will delete all existing data on the disks, including existing partitions!**

**10.** Keep selecting **"Skip for now"** when the **"Upgrade to Ubuntu Pro"** section appears you press **enter** on the **done** button

**11.** The username **`"admin"`** is reserved for use by the system, to use in the first place, so we are going to create a **temporary user** which we will **delete later**. Complete the profile configuration form with the following.

⚠️ This is an IMPORTANT step!

    > name: temp
    > user: temp
    > server name: minibolt
    > password: PASSWORD [A]

**12.** Press **enter** to check **"Install OpenSSH server"** by pressing the **enter** key, and down to select the **"Done"** box and press **enter** again.

⚠️ This is an IMPORTANT step!

**13.** If you want to preinstall some additional software **(not recommended)**, select them, if not, press **"done"** directly to jump to the next step.

**14.** Now all before configurations will be applied and the system installed. This would be a few minutes depending on the hardware used. You can show extended logs by pressing **[View full log]** if you want.

⌛ Wait until the installation finishes, when it happens, **"Reboot now"** will appear. Select it and press **enter**.

**15.** When the prompt shows you **"Please remove the installation medium, then press ENTER"**, extract the pen drive of the PC and press **enter** finally.

🥳 Now the PC should reboot and show you the prompt to log in. You can disconnect the keyboard and the screen of the MiniBolt node, and proceed to connect remotely from your regular computer to continue with the installation ✔️

![Demo install OS gif](../../resources/demo-install-os.gif)

⚠️ This GIF is a recreation of a scenario made with a virtual machine, **VBOX_HARDDISK_**... is the **example name** for the name of the disk. In your case, this probably will not match exactly

<br /><br />

---

Next: [Remote access >>](remote-access.md)
