# MQTT Firmware (Direct Observer)

Flash observer firmware directly onto a supported board. The device connects to WiFi and publishes mesh traffic to MQTT brokers without a host computer.

## Firmware Downloads

Pick your board, role, and flash type to get the right firmware image.

<div id="fw-picker" style="margin: 1.5em 0;">
  <div style="display: flex; flex-wrap: wrap; gap: 1em; margin-bottom: 1em;">
    <div style="flex: 1; min-width: 160px;">
      <label for="fw-board" style="display: block; font-weight: 600; margin-bottom: 0.3em; font-size: 0.85em; text-transform: uppercase; letter-spacing: 0.05em; opacity: 0.7;">Board</label>
      <select id="fw-board" style="width: 100%; padding: 0.5em; border-radius: 6px; border: 1px solid var(--md-default-fg-color--lightest); background: var(--md-code-bg-color); color: var(--md-default-fg-color); font-size: 0.95em;">
        <option value="heltec-v3">Heltec V3</option>
        <option value="heltec-v4-oled">Heltec V4 OLED</option>
      </select>
    </div>
    <div style="flex: 1; min-width: 160px;">
      <label for="fw-role" style="display: block; font-weight: 600; margin-bottom: 0.3em; font-size: 0.85em; text-transform: uppercase; letter-spacing: 0.05em; opacity: 0.7;">Role</label>
      <select id="fw-role" style="width: 100%; padding: 0.5em; border-radius: 6px; border: 1px solid var(--md-default-fg-color--lightest); background: var(--md-code-bg-color); color: var(--md-default-fg-color); font-size: 0.95em;">
        <option value="repeater">Repeater</option>
        <option value="room-server">Room Server</option>
      </select>
    </div>
    <div style="flex: 1; min-width: 160px;">
      <label for="fw-type" style="display: block; font-weight: 600; margin-bottom: 0.3em; font-size: 0.85em; text-transform: uppercase; letter-spacing: 0.05em; opacity: 0.7;">Flash Type</label>
      <select id="fw-type" style="width: 100%; padding: 0.5em; border-radius: 6px; border: 1px solid var(--md-default-fg-color--lightest); background: var(--md-code-bg-color); color: var(--md-default-fg-color); font-size: 0.95em;">
        <option value="merged">First Flash (Merged)</option>
        <option value="update">Update (OTA)</option>
      </select>
    </div>
  </div>
  <div id="fw-result" style="padding: 1em 1.2em; border-radius: 8px; border: 2px solid var(--md-accent-fg-color); background: var(--md-code-bg-color);"></div>
</div>

<script>
(function() {
  var DATE = "20260515";
  var BASE = "firmware/";

  function boardLabel(val) {
    return val === "heltec-v3" ? "Heltec V3" : "Heltec V4 OLED";
  }
  function roleLabel(val) {
    return val === "repeater" ? "Repeater" : "Room Server";
  }
  function typeLabel(val) {
    return val === "merged" ? "First Flash (Merged)" : "Update (OTA)";
  }

  function update() {
    var board = document.getElementById("fw-board").value;
    var role  = document.getElementById("fw-role").value;
    var type  = document.getElementById("fw-type").value;
    var file  = "meshcore-ca-" + board + "-" + role + "-" + type + "-" + DATE + ".bin";
    var href  = BASE + file;

    document.getElementById("fw-result").innerHTML =
      '<div style="margin-bottom: 0.6em;">' +
        '<strong>' + boardLabel(board) + '</strong> &middot; ' +
        roleLabel(role) + ' &middot; ' + typeLabel(type) +
      '</div>' +
      '<div style="font-family: var(--md-code-font-family); font-size: 0.85em; opacity: 0.7; margin-bottom: 0.8em;">' +
        file +
      '</div>' +
      '<a href="' + href + '" download ' +
        'style="display: inline-block; padding: 0.6em 1.5em; border-radius: 6px; ' +
        'background: var(--md-accent-fg-color); color: var(--md-accent-bg-color); ' +
        'font-weight: 600; text-decoration: none;">' +
        '⬇ Download Firmware</a>';
  }

  document.getElementById("fw-board").addEventListener("change", update);
  document.getElementById("fw-role").addEventListener("change", update);
  document.getElementById("fw-type").addEventListener("change", update);
  update();
})();
</script>

??? note "All firmware files"
    Naming convention: `meshcore-ca-{board}-{role}-{type}-{date}.bin`

    **Heltec V3**

    | Role | Merged (First Flash) | Update (OTA) |
    |------|----------------------|--------------|
    | Repeater | [meshcore-ca-heltec-v3-repeater-merged-20260515.bin](firmware/meshcore-ca-heltec-v3-repeater-merged-20260515.bin) | [meshcore-ca-heltec-v3-repeater-update-20260515.bin](firmware/meshcore-ca-heltec-v3-repeater-update-20260515.bin) |
    | Room Server | [meshcore-ca-heltec-v3-room-server-merged-20260515.bin](firmware/meshcore-ca-heltec-v3-room-server-merged-20260515.bin) | [meshcore-ca-heltec-v3-room-server-update-20260515.bin](firmware/meshcore-ca-heltec-v3-room-server-update-20260515.bin) |

    **Heltec V4 OLED**

    | Role | Merged (First Flash) | Update (OTA) |
    |------|----------------------|--------------|
    | Repeater | [meshcore-ca-heltec-v4-oled-repeater-merged-20260515.bin](firmware/meshcore-ca-heltec-v4-oled-repeater-merged-20260515.bin) | [meshcore-ca-heltec-v4-oled-repeater-update-20260515.bin](firmware/meshcore-ca-heltec-v4-oled-repeater-update-20260515.bin) |
    | Room Server | [meshcore-ca-heltec-v4-oled-room-server-merged-20260515.bin](firmware/meshcore-ca-heltec-v4-oled-room-server-merged-20260515.bin) | [meshcore-ca-heltec-v4-oled-room-server-update-20260515.bin](firmware/meshcore-ca-heltec-v4-oled-room-server-update-20260515.bin) |

## Prerequisites

- A supported LoRa board (Heltec V3 or Heltec V4 OLED)
- 2.4 GHz WiFi network credentials
- Your 3-character IATA region code (e.g. `YOW` for Ottawa, `YYZ` for Toronto)

## Flashing

1. Pick your board, role, and flash type from the picker above and download the firmware
2. Flash using the [MeshCore Flasher](https://flasher.meshcore.dev/) or your preferred ESP flashing tool

## CLI Setup

After flashing, connect to the device's admin CLI (serial or web) and run the following setup commands. Replace `YOW` with your region code and fill in your WiFi credentials:

```
set name YOW-Repeater-01
set mqtt.iata YOW
set wifi.ssid YourWiFiNetwork
set wifi.pwd YourWiFiPassword
set wifi.powersave none
set mqtt.status on
set mqtt.packets on
set bridge.enabled on
set mqtt.rx on
set mqtt.tx advert
set repeat on
reboot
```

!!! note "Room Servers"
    For room server roles, change the name (e.g. `YOW-Room-Server-01`) and omit `set repeat on`.

## Broker Slot Configuration

After the initial setup, configure broker slots to point at the MeshCore.ca MQTT pair. Clear all six slots first, then assign:

```
set mqtt1.preset none
set mqtt2.preset none
set mqtt3.preset none
set mqtt4.preset none
set mqtt5.preset none
set mqtt6.preset none
set mqtt1.preset custom
set mqtt1.server wss://mqtt1.meshcore.ca:443/mqtt
set mqtt1.port 443
set mqtt1.audience mqtt1.meshcore.ca
set mqtt2.preset custom
set mqtt2.server wss://mqtt2.meshcore.ca:443/mqtt
set mqtt2.port 443
set mqtt2.audience mqtt2.meshcore.ca
```

## Verify

Run these commands to confirm everything is set correctly:

```
get name
get mqtt.origin
get mqtt.iata
get wifi.status
get mqtt.packets
get bridge.enabled
get mqtt.rx
get mqtt.tx
get mqtt.status
get mqtt1.preset
get mqtt2.preset
get mqtt3.preset
```

After a few minutes, confirm your observer appears on:

- [CoreScope Observers](https://mqtt.canadaverse.org/)
- [CoreScope Packets](https://mqtt.canadaverse.org/)
- [Canadaverse Map](https://canadaverse.org/meshcore-map.html)

## Useful Links

- [MeshCore Flasher](https://flasher.meshcore.dev/)
- [MeshCore Config Tool](https://config.meshcore.dev/)
- [MeshCore CLI Docs](https://meshcore.dev/docs/cli)
- [Firmware Manifest](https://canadaverse.org/firmware/manifest.json)
