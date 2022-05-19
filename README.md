# EFI-X99-F8-OPENCORE
This file contains all the files needed to setup a working machine on macOS Monterey.

Follow down all the specs of my rig and it's working state:

```
Mobo: HUANANZHI X99 F8
CPU: Xeon E5 2699 V3 (18-cores 36-threads 45MB cache)
GPU: RX 560 4GB HUANANZHI
RAM: 64GB - 4x 16GB DDR4 2133Mhz Atermiter
NVME: 1TB NVME M.2 XrayDisk
NVME: 1TB NVME Netac NV3000
Wifi/BT: Fenvi FV-HB1200 Wi-fi 2.5/5GHz BT4.0 PCI-E
OS: macOS Monterey 12.3.1
SMBIOS: iMacPro1,1
```

What's working: Everything
```
GPU Acceleration - Working HDMI and 4k Resolution OOB - haven't tested any DP
Audio - Working but only after setting the "layout-id" to "7"
Wi-fi - Working
Bluetooth - Working but only after setting the BT card as "Internal" and disconnect the USB2.0 case pins from motherboard
USB3 - All USB 3.0 ports are working
AirDrop - Working after Bluetooth setup
iMessage/Facetime - Working
```

---

**BIOS**

First you have to go into your BIOS and follow those steps in order one by one.

1. BIOS Setup Part 1:
```
Advanced > ACPI Setting > ACPI Sleep State > [Suspend Disabled]

Advanced > NCT5532D Super IO Configuration > Serial Port 1 Configuration > Serial Port > [Disabled]

Advanced > CSM Configuration > Boot Option Filter > [Disabled]
Advanced > CSM Configuration > Storage  > [UEFI]
Advanced > CSM Configuration > Video > [UEFI]

Advanced > USB Configuration > XHCI Hand-Off > [Enabled]
Advanced > USB Configuration > EHCI Hand-Off > [Enabled]

IntelCRSetup > Processor Configuration > Hyper-Threading [All] > [Enabled]
IntelCRSetup > Processor Configuration > Execute Disable Bit > [Enabled]
IntelCRSetup > Processor Configuration > MSR Lock Control > [Disabled]
```
**REBOOT**

2. BIOS Setup Part 2:  
  
Go back to BIOS Setup once again and on `Advanced` set `CSM Support` to `Disabled`:

```
Advanced > CSM Configuration > CSM Support > [Disabled]
```

****REBOOT****

And now you should be able to boot from Opencore.

---

**Proof**

![GPU](Proof/GPU.png?raw=true)
![Alt text](Proof/Audio.png?raw=true)
![Alt text](Proof/Bluetooth.png?raw=true)
![Alt text](Proof/USB.png?raw=true)
![Alt text](Proof/RAM.png?raw=true)
![Alt text](Proof/NVME.png?raw=true)

