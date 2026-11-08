# Meshcore Shopping List
*originally by [ExplodingLemur](https://mstdn.social/@ExplodingLemur@mastodon.online)*

Meshcore in the US operates in the 902-928MHz frequency band.  Make sure you get a device that’s designed for use within the US.  There are many more devices available than listed here but we wanted to provide recommendations that would give the best out-of-the-box experience.  Everything below comes with an enclosure and battery and charges via USB-C.  Products available via Amazon (Prime) and Rokland will have tariffs already paid and will have faster shipping.  Seeed has some products available from a US warehouse with tariffs paid and fast shipping, make sure to check where they’re shipping from.

## Portable

You will need one of these to participate in the mesh.  They have the special radio required to talk to other devices.  Portable devices live in your pocket, on a belt clip, stuck to your phone, or otherwise on or near your person to keep you connected to the mesh.  Devices with an external antenna will have better performance than those with an internal antenna.  You can also swap external antennas to optimize for compactness or performance.  An internal GPS allows for position beacons when your phone is not connected but you can always disable this feature for location privacy.

**Portable devices come in two flavors: Companions, and Standalone.**

### Companion

These use your phone as a display and keyboard via Bluetooth.  A few have small displays but they’re more for showing device status than following conversations.  These are the cheapest option and all you need along with your phone to get onto the mesh network.

| Model | Price | Weather-proof | Screen | GPS | Antenna |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Seeed Wio Tracker L1 Pro | [\$48 (seeed)](https://www.seeedstudio.com/Wio-Tracker-L1-Pro-for-Meshcore-p-6717.html) [\$60 (Amazon)](https://www.amazon.com/seeed-studio-L1-Pro-Tracker/dp/B0FNCS5ST1) | No | OLED | Yes | External |
| Seeed SenseCap MeshTracker X1 | [\$50 (seeed)](https://www.seeedstudio.com/sensecap-meshtracker-x1-meshtastic-gps-tracker-p-6935.html) | Yes | None | Yes | Internal |
| Lilygo T-Echo | [\$63 (Amazon)](https://www.amazon.com/LILYGO-Wireless-Meshtastic-Development-NRF52840/dp/B0B658DZ9Z)[\$70 (Rokland)](https://store.rokland.com/products/lilygo-ttgo-meshtastic-t-echo-white-bme280-lora-sx1262-wireless-module-915mhz-nrf52840-gps-rtc-nfc-for-arduino) | No | E-Ink | Yes | External |
| Heltec Mesh Node T1 | [\$40 (Heltec)](https://heltec.org/project/mesh-node-t1/) | Yes | LCD | Yes | Internal |
| Heltec MeshPocket Qi2 | [\$49 (Heltec)](https://heltec.org/project/meshpocket/)[\$69 (Amazon)](https://www.amazon.com/Heltec-MeshPocket-Meshtastic-Compatible-Emergency/dp/B0F7LD3BQG)[\$79 (Rokland)](https://store.rokland.com/collections/heltec-products/products/heltec-meshpocket-qi2-magnetic-charging-power-bank-meshtastic-compatible) | No | E-Ink | No | Internal |
| Elecrow ThinkNode M1 | [\$54 (Elecrow)](https://www.elecrow.com/thinknode-m1-meshtastic-lora-signal-transceiver-powered-by-nrf52840-with-154-screen-support-gps.html)[\$63 (Rokland)](https://store.rokland.com/collections/elecrow/products/elecrow-thinknode-m1-lora-meshtastic-radio-1-54-epd-screen-gps-nrf52840)[\$77 (Amazon)](https://www.amazon.com/ELECROW-Transceiver-Compatible-Meshtastic-nRF52840/dp/B0FPLWYB8R) | No | E-Ink | Yes | External |

### Standalone

These devices have keyboards and screens that let you use them fully independently of a phone (though they can still pair with your phone via Bluetooth since the on-device interface can be a bit limited).  If you remember two-way pagers, that’s what these look like (also, remember to take your ibuprofen - beep beep beep!).

| Model | Price | Weather-proof | Screen | GPS | Antenna |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Lilygo T-Lora Pager | [\$87 (Lilygo)](https://lilygo.cc/products/t-lora-pager-meshcore?variant=53105158521013)[\$115 (Rokland)](https://store.rokland.com/products/lilygo-t-lora-pager-us-915-mhz-lora-esp32-s3-handheld-aiot-programmable-development-device-k257-01) | No | E-Ink | Yes | External |
| Lilygo T-Deck Plus | [\$71 (Lilygo)](https://lilygo.cc/products/t-deck-plus-1?variant=44897766408373)[\$100 (Rokland)](https://store.rokland.com/products/lilygo-t-deck-portable-microcontroller-programmer-lora-915-mhz-h642?variant=42283977834579) | No | LCD | Yes | Internal |
| Lilygo T-Deck Plus (ext. ant.) | [\$76 (Lilygo)](https://lilygo.cc/products/t-deck-plus-1?variant=45420343918773)[\$80 (Amazon)](https://www.amazon.com/LILYGO-ESP32-S3-Computer-2-8-inch-Development/dp/B0DSFTKT5V)[\$110 (Rokland)](https://store.rokland.com/products/lilygo-t-deck-portable-microcontroller-programmer-lora-915-mhz-h642?variant=43009954906195) | No | LCD | Yes | External |
| Lilygo T-Deck Pro | [\$95 (Lilygo)](https://lilygo.cc/products/t-deck-pro)[\$115 (Amazon)](https://www.amazon.com/LILYGO-T-Deck-Wireless-Development-Viewing/dp/B0F32PQ8SD) | No | E-Ink | Yes | Internal |
| Elecrow ThinkNode M9 | [\$75 (Elecrow)](https://www.elecrow.com/thinknode-m9-meshcore-communication-terminal-with-full-keyboard-2-4inch-lcd-esp32-s3-lr1110-gps-2300mah.html) | No | LCD | Yes | External |

## Repeater

These optional devices are for fixed-location use to increase coverage of the mesh network.  If you’re not able to reach the mesh from where you are then a strategically-placed repeater might help, but it depends on several factors.  They typically have solar panels and batteries to make them fully self-sufficient for outdoor operation.  The higher up they are, the wider an area they will cover.  GPS is not strictly necessary as repeaters don’t move around but it can be useful to have it set its clock automatically.  They usually come with some kind of external antenna but you can replace it with one more suited to your deployment environment.

| Model | Price | Solar | GPS | Battery |
| :---- | :---- | :---- | :---- | :---- |
| Seeed SenseCAP P1 | [\$78 (seeed)](https://www.seeedstudio.com/SenseCAP-Solar-Node-P1-for-Meshtastic-LoRa-p-6425.html) | 5W | No | 4x 18650\* |
| Seeed SenseCAP P1 Pro | [\$94 (seeed)](https://www.seeedstudio.com/SenseCAP-Solar-Node-P1-Pro-for-Meshcore-p-6741.html)[\$140 (Amazon)](https://www.amazon.com/SenseCAP-Solar-Node-P1-Pro-Communication/dp/B0FMDHBWX8) | 5W | Yes | 4x 18650 |
| Heltec MeshTower V2 | [\$109 (Heltec)](https://heltec.org/project/meshtower/) | 10W | Yes | 3x 18650 |
| Elecrow ThinkNode M6 | [\$80 (Elecrow)](https://www.elecrow.com/thinknode-m6-outdoor-solar-power-for-meshtastic-powered-by-nrf52840-supports-gps.html) | 6W | Yes | 2x 18650 |
| RAK Wismesh Repeater Mini | [\$100 (Rokland)](https://store.rokland.com/products/wismesh-repeater-mini-reliable-coverage-expansion-for-smart-networks) | Yes | No | Yes |

\* batteries not included
