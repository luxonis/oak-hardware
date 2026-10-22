# OAK 4 FFC

Design resources for the **BK3498 OAK 4 FFC carrier board** and its **BK6970 PoE power board**. The carrier connects an OAK 4 SOM to five FFC camera interfaces and provides Ethernet, USB, CAN, storage, and expansion connections.

The OAK 4 FFC SKU family is `OAK-4-FFC-DEVKIT`, and `OAK-4-FFC-BAREBONE`. The OAK 4 SOM module SKU is `OAK-4-SOM`.

This directory contains carrier and PoE board designs, plus reusable SoM connector libraries. The OAK 4 SOM internal design, module firmware, camera boards, and enclosure are outside this release's scope.

## Design files

| Resource | Description |
| --- | --- |
| [BK3498 Altium project](Source%20files/BK3498_R1D0.zip) | Carrier PCB, schematics, harnesses, Draftsman documents, ActiveBOM, and assembly/fabrication output jobs. |
| [BK3498 schematic PDF](Docs/BK3498_R1D0.pdf) | Readable carrier schematic, 21 pages. |
| [BK6970 Altium project](Source%20files/BK6970_R1D0.zip) | PoE PCB, schematics, harnesses, Draftsman documents, and ActiveBOM. |
| [BK6970 schematic PDF](Docs/BK6970_R1D0.pdf) | Readable PoE board schematic, four pages. |
| [OAK 4 SOM datasheet](Docs/OAK-4-SOM_R7.pdf) | Module integration information, pinouts, electrical limits, and mechanical drawings; revision 2.2. |
| [Connector A](Libraries/OAK4-MAX_Connector_A.zip), [B](Libraries/OAK4-MAX_Connector_B.zip), [C](Libraries/OAK4-MAX_Connector_C.zip) | Altium symbols and footprints, editable library sources, and compiled integrated libraries for the three SoM connectors. |

The `OAK4-MAX` names in the library ZIPs are retained from the supplied exports. These are SoM mating-connector libraries, not additional board projects.

## Carrier interfaces

The schematic routes five four-lane MIPI CSI camera interfaces through 26-pin, bottom-contact FFC connectors, with camera control, clock, synchronization, and strobe signals. The mapping below follows connected CSI nets rather than the nearby descriptive headings.

| Carrier connector | SoM camera interface | Schematic sheet |
| --- | --- | --- |
| J8 | CSI0 | `FFC_Aux` |
| J11 | CSI2 | `FFC_Stereo` |
| J7 | CSI3 | `FFC_Stereo` |
| J10 | CSI4 | `FFC_Center` |
| J9 | CSI5 | `FFC_Aux` |

Other circuitry includes PCIe-to-Ethernet with an M12 connector, USB Type-C, an M8 auxiliary interface, CAN, microSD, EEPROM, IMU/magnetometer options, and expansion signals. Fitted components depend on the assembly variant; simultaneous camera operation and supported sensors also depend on the SoM software configuration.

BK6970 provides the separate PoE power-conversion circuitry and a `12V_PoE` rail. Use its schematic together with the carrier power and connector sheets when integrating it.

## Opening the source

Extract each board ZIP into its own directory and open its `.PrjPcb` in Altium Designer. BK3498's project is named `BK3498_2026-08-18T14_13_01_UTC.PrjPcb`; BK6970's is `BK6970.PrjPcb`.

Each connector ZIP includes `.SchLib`, `.PcbLib`, `.LibPkg`, and `.IntLib` files. Use the editable libraries for adaptations or the integrated library for component placement. Managed library references remain in the board projects; the connector exports alone are not a complete project library set.

## Release licensing

The [repository README](https://github.com/luxonis/oak-hardware/blob/master/README.md) describes dual licensing under [MIT](https://github.com/luxonis/oak-hardware/blob/master/LICENSE) or the [KiCad Libraries License](https://github.com/luxonis/oak-hardware/blob/master/LICENSE.KiCad.md). Coverage of this new bundle and any embedded third-party assets must be confirmed before publication. Both boards' Draftsman documents retain proprietary/confidential notices, and the SoM datasheet retains an all-rights-reserved notice; those need an explicit release decision and consistent notices.
