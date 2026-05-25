# Heltec V3 Repeater Firmware Source

This page links the full source tree for the published Heltec V3 direct MQTT observer repeater firmware:

- `meshcore-ca-heltec-v3-repeater-20260521-merged.bin`
- `meshcore-ca-heltec-v3-repeater-20260521-update.bin`
- embedded firmware string: `v1.15-meshcoreCA-0521-f1b4b75`
- embedded build date: `21-May-2026`

## Full Source

The complete source tree is published on the `heltec-v3-repeater-source-20260521` branch:

[`n30nex/MeshCore-Canada/tree/heltec-v3-repeater-source-20260521`](https://github.com/n30nex/MeshCore-Canada/tree/heltec-v3-repeater-source-20260521)

The branch root contains `README.MeshCore-Canada-Heltec-V3-Repeater.md` with the firmware hashes and build target.

## Published Hashes

```text
a1b2ae4b4d1a60dddb96e14285fe2912c37084ab8d515414b10bffa7d2fe5ce0  meshcore-ca-heltec-v3-repeater-20260521-merged.bin
2f0b6778006f4b4c0368b0ed80bdedb8c1f89ff3b3324f3c6d3a7879c27d46ad  meshcore-ca-heltec-v3-repeater-20260521-update.bin
```

## Build Target

```bash
pio run -e Heltec_v3_repeater_observer_mqtt
```

The source branch was compiled successfully with that target before publication.
