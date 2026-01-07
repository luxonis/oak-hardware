# OAK Open Source Hardware

[![Discord](https://img.shields.io/discord/790680891252932659?label=Discord)](https://discord.gg/luxonis)
[![Forum](https://img.shields.io/badge/Forum-discuss-orange)](https://discuss.luxonis.com/)
[![Docs](https://img.shields.io/badge/Docs-DepthAI_Hardware-yellow)](https://docs.luxonis.com/projects/hardware)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

This repository contains OAK Open Source Hardware designs, including Altium design files, documentation, and pictures. This repository is for anyone interested in developing with the OAK SoM or anyone interested in understanding more about the embedded hardware that powers OAK devices. An open source, community KiCad folder is also available for sharing KiCad based designs and components.

The designs are Dual Licensed under [MIT](LICENSE) or [KiCad Libraries License](LICENSE.KiCad.md)

# POE Designs

## [OAK-D-POE | SJ2088POE](https://github.com/luxonis/oak-hardware/tree/master/SJ2088POE_PoE_Board)

This board is the basis for the OAK-D-POE.  And it is the equivalent of the BW1098OBC/BW1098OAK, but with POE instead of USB.  So 3 onboard cameras (1x onboard IMX378 12MP autofocus color camera, 2x global shutter grayscale for stereo depth), with the stereo baseline being 7.5cm (just like BW1098OBC/BW1098OAK/OAK-D).

![IMG_3045](https://user-images.githubusercontent.com/32992551/109262631-1cc40780-77bf-11eb-9263-034dd1b55ad4.JPG)

This design is in progress.  When complete it will support the DepthAI API over Ethernet, and some additional features like direct RTSP streaming.

## [OAK-1-POE | SJ2096POE](https://github.com/luxonis/oak-hardware/tree/master/SJ2096POE_R0M0E0)

This is the basis for OAK-1-POE.  It is the equivalent of the BK1096_OAK, with with POE instead of USB.  So 1x onboard IMX378 12MP autofocus color camera.

![IMG_3041](https://user-images.githubusercontent.com/32992551/109261978-fce01400-77bd-11eb-8895-2a5083a61013.JPG)

This design is in progress.  When complete it will support the DepthAI API over Ethernet, and some additional features like direct RTSP streaming.

## [BW2098POE](https://github.com/luxonis/oak-hardware/tree/master/BW2098POE_PoE_Board)
The [BW2098POE repository](https://github.com/luxonis/oak-hardware/tree/master/BW2098POE_PoE_Board) contains open hardware designed by Luxonis, and meant to be used as a baseboard for the [Luxonis](https://www.luxonis.com/depthai) BW2099 OAK SoM. The BW2098POE baseboard offers full 802.3af, Class 3 PoE compliance with 1000BASE-T speeds, along with user-selectable external power from a 5V barrel jack. The Luxonis BW0249 12MP RGB camera module can be connected via the 26-pin FFC interface, which exposes a 4-lane MIPI CSI-2 channel directly into the Myriad X on the BW2099 module for processing. Data can also be streamed to a host via USB 3.1 Gen1 (Type-C). Finally, the BW2098POE board exposes boot selection switches, allowing the end user to boot the BW2099 module from USB or the on-board eMMC or NOR flash.

![](BW2098POE_PoE_Board/Images/BW2098POE_R1M1E1_front.jpg)

# Integrated Raspberry Pi Designs

## [DM1097](https://github.com/luxonis/oak-hardware/tree/master/DM1097_DepthAI_Compute_Module_4#dm1097_r0m0e0-depthai-for-compute-module-4)
The [DM1097](https://github.com/luxonis/oak-hardware/tree/master/DM1097_DepthAI_Compute_Module_4#dm1097_r0m0e0-depthai-for-compute-module-4) contains the design files for DepthAI with an integrated/onboard [Raspberry Pi Compute Module 4](https://www.raspberrypi.org/products/compute-module-4/?variant=raspberry-pi-cm4001000).
The DM1097 combines a host and the Luxonis OAK SoM to allow for fully integrated solution for real-time spatial AI. It is effectively the same as the BW1097, below, but with a Pi 4 computer module instead of a Pi 3 compute module.

![image](https://user-images.githubusercontent.com/32992551/109263101-edfa6100-77bf-11eb-85ef-037fe24e9975.png)

## [BW1097](BW1097_DepthAI_Compute_Module)
The [BW1097 repository](/BW1097_DepthAI_Compute_Module) contains open hardware designed by Luxonis, and meant to be used as a baseboard for the [Luxonis](https://www.luxonis.com/depthai) BW1099 OAK SoM and the [Raspberry Pi Compute Module 3+](https://www.raspberrypi.org/products/compute-module-3-plus/). Based on the Raspberry PI CMIO board, the BW1097 combines a host and the Luxonis OAK SoM to allow for fully integrated solution for real-time spatial AI.

![](BW1097_DepthAI_Compute_Module/Images/BW1097_R1M1E2_transparent_crop.png)

# USB Designs

## [OAK-D | BW1098OAK](https://github.com/luxonis/oak-hardware/tree/master/BW1098OAK_USB3C#bw1098oak-usb3c-baseboard)

This board is used in the depthai product known as the OpenCV AI Kit with Depth, OAK-D:

![image](https://user-images.githubusercontent.com/32992551/109374027-aaf7c680-786f-11eb-9e96-90e9928d161c.png)

## [BW1098OBC](BW1098OBC_DepthAI_USB3C)
The [BW1098OBC repository](BW1098OBC_DepthAI_USB3C) contains open hardware designed by Luxonis, and meant to be used as a baseboard for the [Luxonis](https://www.luxonis.com/depthai) BW1099 OAK SoM. The BW1098OBC baseboard has three on-board cameras which implement stereo and RGB vision, piped directly into the OAK SoM for depth and AI processing. The data is then output to a host via USB 3.1 Gen1 (Type-C).

![](BW1098OBC_DepthAI_USB3C/Images/BW1098OBC_R1M0E1_front.png)

# USB designs with attachable FFC camera boards

The 1090 is our updated version from the common issues customers have had with BW1098FFC. (We will keep selling the 1098FFC, for folks who have that connector type.)
Improvements/changes:

- More robust mechanical connection (a LOT more robust)
- ESD protection added.
- Standardized pinout (All 3 camera connectors have the same pinout - meaning that mix/match can be done using 2x 2-lane MIPI and 1x 4-lane MIPI)
- Capability to use with ArduCam cameras w/out an adapter board (including clock sync and trigger sync).

Below is a flow-chart showing the evolution of this design over time based on customer feedback/needs.

![](DM1090FFC_DepthAI_USB3/Images/Flowchart_FFC.png)

More information about each design can be found in corresponding repositories.

## [DM1090FFC](DM1090FFC_DepthAI_USB3)

The [DM1090FFC repository](DM1090FFC_DepthAI_USB3) contains open hardware designed by Luxonis, and meant to be used as a baseboard for the [Luxonis](https://www.luxonis.com/depthai) BW1099 OAK SoM. The DM1090FFC baseboard has three FFC interfaces which allow for two [DM0250TG](DM0250TG_DepthAI_Mono_Camera) camera modules (stereo pair) and one [DM0249](DM0249_DepthAI_RGB_Camera) RGB camera module.
Besides Luxonis camera modules, several Arducam CCMs can be connected to [DM1090FFC](DM1090FFC_DepthAI_USB3).
Please note that only revision R1 and above (R1M1E1) ([DM0250TG](DM0250TG_DepthAI_Mono_Camera) and [DM0249](DM0249_DepthAI_RGB_Camera)) cameras with 26-pin FFC connectors can be connected to [DM1090FFC](DM1090FFC_DepthAI_USB3).

![](DM1090FFC_DepthAI_USB3/Images/DM1090FFC-KIT.jpg)

## [BW1094](BW1094_DepthAI_HAT)
The [BW1094 repository](BW1094_DepthAI_HAT) contains open hardware designed by Luxonis, and meant to be used as a baseboard for the [Luxonis](https://www.luxonis.com/depthai) BW1099 OAK SoM and as a HAT for the [RPi "B" models](https://www.raspberrypi.org/products/). The BW1094 baseboard has three FFC interfaces which allow for two [BG0250TG](BG0250TG_DepthAI_Mono_Camera) camera modules (stereo pair) and one [BG0249](BG0249_DepthAI_RGB_Camera) RGB camera module. The GPIO interface from the Raspberry Pi Model B variants is passed through the BW1094 with the exception of the 5V pins, GND pins, and [BCM GPIO26 (pin 37)](https://www.raspberrypi.org/documentation/usage/gpio/), which is used as a way for the Raspberry Pi to reset the OAK SoM, parallel to the RST button.

![](BW1094_DepthAI_HAT/Images/BW1094_R0M0E0_front.png)

## [BK1096](BK1096_OAK-1_Modular)
The [BK1096 repository](/BK1096_OAK-1_Modular) contains open hardware designed by Luxonis, and meant to be used as a baseboard for the [Luxonis](https://www.luxonis.com/depthai) BW1099 OAK SoM. The BK1096 baseboard offers a quick and simple way to add USB3 Type-C device power and connectivity, and a single 12MP RGB camera module to the OAK SoM.

![](BK1096_OAK-1_Modular/Images/BK1096_R0M0E0_front.jpg)

# Cameras and Camera Adapter Boards

## [BG0249](BG0249_DepthAI_RGB_Camera)
The [BG0249 repository](BG0249_DepthAI_RGB_Camera) contains open hardware designed by Luxonis. The BW0249 is a carrier board for the Sunny A12N02A IMX378 camera module, and is designed to be compatible with the [BW1094](BW1094_DepthAI_HAT) and [BW1098FFC](BW1098FFC_DepthAI_USB3) baseboards. A 26-pin FFC is used to carry 5V power, 4-lane MIPI, I2C, and other control signals between the BW0249 and the controller baseboards.

![](BG0249_DepthAI_RGB_Camera/Images/BG0249_R0M0E0_front.png)

## [BG0250TG](BG0250TG_DepthAI_Mono_Camera)
The [BG0250TG repository](BG0250TG_DepthAI_Mono_Camera) contains open hardware designed by Luxonis. The BW0250TG is a carrier board for the Sunny TG161B or AN01V32 OV9282 camera module, and is designed to be compatible with the [BW1094](BW1094_DepthAI_HAT) and [BW1098FFC](BW1098FFC_DepthAI_USB3) baseboards. A 20-pin FFC is used to carry 5V power, 2-lane MIPI, I2C, and other control signals between the BW0250TG and the controller baseboards. A single BG0250TG is typically paired with another to create a stereo camera pair.

![](BG0250TG_DepthAI_Mono_Camera/Images/BG0250TG_R0M0E0_front.png)


## [BW0253_R0M0E0 Raspberry Pi HQ Cam Adapter Board](/BW0253_R0M0E0_RPIHQ_ADAPTER)
![](BW0253_R0M0E0_RPIHQ_ADAPTER/Images/RPI_HQ_CAM_SYSTEM_2020-May-14_08-35-31PM-000_CustomizedView42985702451.png)

The [BW0253_R0M0E0](/BW0253_R0M0E0_RPIHQ_ADAPTER) is an adapter board to allow the [Raspberry Pi HQ camera](https://www.raspberrypi.org/products/raspberry-pi-high-quality-camera/) to physically interface to the DepthAI RGB camera port on the [BW1098FFC](https://github.com/luxonis/oak-hardware/tree/master/BW1098FFC_DepthAI_USB3).

This allows using DepthAI with all sorts of lens combinations, including variable zoom, variable focus, and even [with a telescope](https://www.tomshardware.com/news/raspberry-pi-high-quality-camera-used-for-out-of-this-world-astrophotography).


![image](https://user-images.githubusercontent.com/32992551/97765359-5fa6f480-1ad7-11eb-85fa-4b9a6d4e30d7.png)
