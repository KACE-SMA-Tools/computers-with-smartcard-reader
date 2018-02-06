# Target
Finds and report all managed Windows PCs in K1000 Inventory with a smartcard reader installed.

## Overview
The script is independent by K1000, so if you don't have KACE SMA in your environment don't worry: the script is still useful!

## Components
* [The Query] This script :innocent:
* [The Report] Kace Systems Management Appliance (AKA 'K1000')


# How does it work
1. The vbs script executes a WMI query over the target device(s) and saves an output file named _smartcard.txt_ (see below in the [Setup section](#setup))
2. The vbs script is scheduled and deployed to the target device(s) via K1000 script (_Online KScript_)
3. A K1000 _Custom Inventory Rule_ reads the output file for every inventoried device and stores the information in the database
4. A scheduled Report (choose your favorite format between HTML, CSV, PDF or Excel) returns only PCs with a smart card reader installed
5. Done!

## Setup

Edit [the script](smartcard.vbs) **line 4** with a path where you want to save the output file. In our environment every PC has a _"C:\Tools"_ directory for service purpose, so i decided to save the output there.