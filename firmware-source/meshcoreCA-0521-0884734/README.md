# MeshCore Canada Firmware Source: meshcoreCA-0521-0884734

This directory publishes the source disclosure for the local MeshCore Canada firmware build identified by filenames containing `v1.15-meshcoreCA-0521-0884734`.

## Source Base

- Upstream source: `https://github.com/agessaman/MeshCore.git`
- Local branch inspected: `canadaverse-mqtt-observer`
- Base commit: `08847342c5148ff68ac7d38f3f1cbd83661b7f8a`
- Local source delta: `meshcoreCA-0521-0884734.patch`

The patch records the local Canada/Canadaverse MQTT observer modifications that were present in the build tree when this disclosure was prepared.

## Reconstructing the Source

```bash
git clone https://github.com/agessaman/MeshCore.git
cd MeshCore
git checkout 08847342c5148ff68ac7d38f3f1cbd83661b7f8a
git apply ../meshcoreCA-0521-0884734.patch
```

## Local Build Files Observed

```text
Heltec_v3_repeater_observer_mqtt-v1.15-meshcoreCA-0521-0884734-merged.bin
Heltec_v3_repeater_observer_mqtt-v1.15-meshcoreCA-0521-0884734.bin
Heltec_v3_room_server_observer_mqtt-v1.15-meshcoreCA-0521-0884734-merged.bin
Heltec_v3_room_server_observer_mqtt-v1.15-meshcoreCA-0521-0884734.bin
LilyGo_T3S3_sx1262_repeater_observer_mqtt-v1.15-meshcoreCA-0521-0884734-merged.bin
LilyGo_T3S3_sx1262_repeater_observer_mqtt-v1.15-meshcoreCA-0521-0884734.bin
LilyGo_T3S3_sx1262_room_server_observer_mqtt-v1.15-meshcoreCA-0521-0884734-merged.bin
LilyGo_T3S3_sx1262_room_server_observer_mqtt-v1.15-meshcoreCA-0521-0884734.bin
T_Beam_S3_Supreme_SX1262_repeater_observer_mqtt-v1.15-meshcoreCA-0521-0884734-merged.bin
T_Beam_S3_Supreme_SX1262_repeater_observer_mqtt-v1.15-meshcoreCA-0521-0884734.bin
heltec_v4_repeater_observer_mqtt-v1.15-meshcoreCA-0521-0884734-merged.bin
heltec_v4_repeater_observer_mqtt-v1.15-meshcoreCA-0521-0884734.bin
heltec_v4_room_server_observer_mqtt-v1.15-meshcoreCA-0521-0884734-merged.bin
heltec_v4_room_server_observer_mqtt-v1.15-meshcoreCA-0521-0884734.bin
```

## Attribution And License

MeshCore is MIT licensed. The upstream `license.txt` remains applicable after applying this local patch. This directory does not replace upstream attribution; it records the local source delta used for the Canada/Canadaverse MQTT observer build.
