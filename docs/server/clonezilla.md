---
layout: default
title: Clonezilla
parent: Server
nav_order: 2
---

# HOW TO SETUP CLONEZILLA FOR UPGRADING SSDs
{: .no_toc }

- TOC
{:toc}

---

## Set up a bootable USB

### Download Clonezilla & Rufus

Go to the Clonezilla website and download the version labled [stable 2.7.0-10](https://clonezilla.org/downloads.php). This is the version that worked best for me. 

Then download the utility program called [rufus](https://rufus.ie/). 

Here's the issue: Clonezilla is pretty old and in my experience only **Rufus** will work to create a bootable USB with Clonezilla. Other programs such as Etcher **DID NOT WORK**.

### Create the bootable USB

Realistically any size USB in 2021 will work for this application. It's hard to find a USB that isn't at least 1 GB in size.

When creating the USB in Rufus, make sure that the USB partition scheme matches the partition scheme of the Windows SSD you are trying to clone. That is, if you are cloning a MBR SSD then the USB needs to be MBR. 

Run Rufus and create the bootable USB with Clonezilla on it. 

### Download MiniTools Partition Wizard

This step **must** be completed before the cloning process. 

After you clone the SSD it will appear that there is "missing space." For example, cloning a 250gb SSD to a 500gb it will appear that nearly half of the space is missing. This is because Clonezilla makes a perfect copy of the original SSD. In order to use the new, empty space on the target SSD, you will have to use [MiniTool Partition Wizard](https://www.partitionwizard.com/free-partition-manager.html) in order to "re-arrange" the partitions on the target (new) drive to then use all the newly acquired free space. 

### SSDs attached to motherboard

Both the original SSD and the target SSD need to be hooked up directly to the motherboard either via sata cables or ports in the case of NVME drives.

Before the cloning process begins, you have to create a simple volume on the target SSD (the new one). 

### Reboot the computer

Make sure that the Clonezilla USB is attached to a the computer. Using the rear I/O yields better results than the front I/O ports. Make sure the original and target SSDs are attached to the motherboard. 

When rebooting, I find it yields better results to hit the "boot order" button on the keyboard rather than the full BIOS screen button. For example, instead of hitting DEL on my keyboard I hit F11. This brings up a simple menu for a one-time boot order priorty of the device you want to use. 

Select the USB with Clonezilla on it. 

### Using Clonezilla

BEN, NEED TO THINK ABOUT HOW TO DO THIS SECTION. WE BOTH KNOW CLONEZILLA IS CLUNKY & AWKWARD TO USE. 

### After Using Clonezilla

After the Clonezilla process is over, shut down the computer. 

Remove the original SSD and the USB so that only the new, target SSD with the larger storage is attached to the motherboard. 

Turn on the PC. If everything goes according to plan, your PC should act exactly the same as before. 

Open the start menu and type `disk partition` to open the program labeled as `create and formate hard drive disk partitions`. This program is called **Disk Management**.

Here you should see that the new SSD with higher capacity is attached, but it is only using the amount of storage from the original SSD. For example a 250gb SSD is only using 120gb. 

### Open MiniTool Partition Wizard. 

BEN, THIS STEP ALSO SLIGHTLY COMPLICATED AND PROBABLY REQUIRES IMAGES. WILL ADD LATER.

### Final Steps

After you have properly expanded the storage using MiniTool Partition Wizard, your journey using Clonezilla is over. 

I suggest keeping the original SSD around for a week or two just in case anything goes wrong with the new SSD. 

After that time period feel free to use the original SSD in another capacity. 
