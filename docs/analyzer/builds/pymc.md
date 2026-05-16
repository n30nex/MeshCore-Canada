# PyMC (Python MeshCore)

Add the MeshCore.ca broker pair to an existing pyMC repeater installation. PyMC connects to your MeshCore device and forwards traffic to MQTT brokers using a YAML config file.

## Prerequisites

- A working pyMC repeater installation
- Your 3-character IATA region code (e.g. `YOW` for Ottawa, `YYZ` for Toronto)

## Configuration

### 1. Set Your IATA Code

In `/etc/pymc_repeater/config.yaml`, set your region code under the MQTT section:

```yaml
mqtt:
  iata_code: YOW
```

### 2. Add the Broker Block

Paste the following under `mqtt.brokers` in your config file:

```yaml
- name: Canadaverse
  enabled: true
  host: mqtt1.meshcore.ca
  port: 443
  transport: websockets
  format: letsmesh
  disallowed_packet_types: []
  retain_status: false
  tls:
    enabled: true
    insecure: false
  use_jwt_auth: true
  audience: mqtt1.meshcore.ca
- name: Canadaverse Backup
  enabled: true
  host: mqtt2.meshcore.ca
  port: 443
  transport: websockets
  format: letsmesh
  disallowed_packet_types: []
  retain_status: false
  tls:
    enabled: true
    insecure: false
  use_jwt_auth: true
  audience: mqtt2.meshcore.ca
```

### 3. Optional Fields

You can also set these optional fields in the `mqtt` section:

```yaml
mqtt:
  owner: "your-public-key"
  email: "you@example.com"
```

### 4. Restart the Service

```bash
sudo systemctl restart pymc-repeater
```

## Quick Reference

| Setting | Value |
|---------|-------|
| Config file | `/etc/pymc_repeater/config.yaml` |
| Primary broker | `mqtt1.meshcore.ca` |
| Backup broker | `mqtt2.meshcore.ca` |
| Port | `443` |
| Transport | `websockets` |
| TLS | Enabled, verified |
| Auth | JWT token (`use_jwt_auth: true`) |
| Format | `letsmesh` |

## Verify

After restarting, head to [Verify Observer Status](../verify.md) to confirm it's reporting correctly.
