# MeshCore.ca Heltec V3 Repeater Firmware Source

This branch publishes the full source tree for the MeshCore.ca Heltec V3 direct MQTT observer repeater firmware identified by:

- `meshcore-ca-heltec-v3-repeater-20260521-merged.bin`
- `meshcore-ca-heltec-v3-repeater-20260521-update.bin`
- embedded firmware string: `v1.15-meshcoreCA-0521-f1b4b75`
- embedded build date: `21-May-2026`
- upstream base: `agessaman/MeshCore` commit `f1b4b75839cc34079987ff526e37f0b2dba251e1`

Observed published binary hashes:

```text
a1b2ae4b4d1a60dddb96e14285fe2912c37084ab8d515414b10bffa7d2fe5ce0  meshcore-ca-heltec-v3-repeater-20260521-merged.bin
2f0b6778006f4b4c0368b0ed80bdedb8c1f89ff3b3324f3c6d3a7879c27d46ad  meshcore-ca-heltec-v3-repeater-20260521-update.bin
```

The Heltec V3 repeater observer environment is `Heltec_v3_repeater_observer_mqtt`. It is configured here with MeshCore.ca broker defaults and USA/Canada radio defaults:

- `mqtt1.meshcore.ca:443/mqtt`
- `mqtt2.meshcore.ca:443/mqtt`
- `910.525 MHz / 62.5 kHz / SF7 / CR5`

Build target:

```bash
pio run -e Heltec_v3_repeater_observer_mqtt
```

MeshCore is MIT licensed. The upstream `license.txt` remains applicable.

Editor/debug log files from the local checkout are omitted from this branch because they are not firmware source.
