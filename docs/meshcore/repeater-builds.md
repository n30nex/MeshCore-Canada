# Repeater Build Guides

!!! info "This page is a work in progress"
    Content coming soon. Want to help? See [Contributing](../contributing.md).

## Overview

Step-by-step guides for building and deploying MeshCore repeaters.

Before placing a repeater, configure it for the MeshCore Canada network:

| Setting | Value |
|---------|-------|
| Radio preset | `USA/Canada (Recommended)` |
| Raw radio values | `910.525 MHz / 62.5 kHz / SF7 / CR5` |
| Path hash mode | `3-byte` |

For repeaters or room servers flashed with 2026-05-21 or newer MeshCore.ca direct MQTT firmware, run:

```text
set path.hash.mode 2
reboot
```

!!! note "Fresh MeshCore.ca firmware flashes"
    The 2026-05-21 and newer MeshCore.ca direct MQTT firmware images already default to the USA/Canada radio preset. If you are updating an older image, reusing a device with retained preferences, or configuring generic firmware, also run `set radio 910.525,62.5,7,5` before installing the repeater on a roof, mast, or remote site.

## Indoor Repeater

<!-- TODO: Parts list, assembly, firmware flash, configuration -->

## Outdoor / Weatherproof Repeater

<!-- TODO: Enclosure options, weatherproofing, mounting -->

## Solar-Powered Remote Repeater

<!-- TODO: Solar panel sizing, battery, charge controller, full build walkthrough -->
