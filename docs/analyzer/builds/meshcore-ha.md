# MeshCore-HA (Home Assistant)

Add the MeshCore.ca broker pair to your Home Assistant MeshCore integration. This connects your HA instance to the Canadian mesh telemetry network.

## Prerequisites

| Requirement | Details |
|-------------|---------|
| Home Assistant | With the MeshCore integration installed |
| MeshCore Node | Connected to HA via USB, BLE, or TCP |
| IATA Code | Your 3-character region code (e.g. `YOW` for Ottawa) |

## Setup

### 1. Open Broker Settings

Navigate to:

**Settings** > **Devices & Services** > **MeshCore** > **Configure** > **Manage MQTT Brokers**

### 2. Configure the Primary Broker

| Field | Value |
|-------|-------|
| Server | `mqtt1.meshcore.ca` |
| Port | `443` |
| Transport | `websockets` |
| Use TLS | :material-check: Enabled |
| TLS Verify | :material-check: Enabled |
| Username / Password | Leave blank |
| Use MeshCore Auth Token | :material-check: Enabled |
| Token Audience | `mqtt1.meshcore.ca` |
| Auth Token TTL | Leave default |
| Payload Mode | `packet` |
| Status Topic | `meshcore/{IATA}/{PUBLIC_KEY}/status` |
| Packets Topic | `meshcore/{IATA}/{PUBLIC_KEY}/packets` |
| Client ID Prefix | Optional |
| Owner Public Key | Optional (TLS verified only) |
| Owner Email | Optional (TLS verified only) |

### 3. Configure the Backup Broker

Add a second broker with the same settings, changing only:

| Field | Value |
|-------|-------|
| Server | `mqtt2.meshcore.ca` |
| Token Audience | `mqtt2.meshcore.ca` |

All other fields remain the same as the primary broker.

### 4. Set Your Region

Make sure your IATA region code is set in the integration. The `{IATA}` placeholder in the topic templates will be replaced with your code (e.g. `YOW`).

!!! tip
    You can find your nearest IATA code on the [Analyzer Overview](../intro.md) page.

## Quick Reference

| Setting | Primary | Backup |
|---------|---------|--------|
| Server | `mqtt1.meshcore.ca` | `mqtt2.meshcore.ca` |
| Port | `443` | `443` |
| Transport | `websockets` | `websockets` |
| TLS | Enabled + Verified | Enabled + Verified |
| Auth | MeshCore JWT Token | MeshCore JWT Token |
| Audience | `mqtt1.meshcore.ca` | `mqtt2.meshcore.ca` |
| Payload Mode | `packet` | `packet` |

## Verify

After saving, head to [Check Your Observer](../verify.md) to confirm it's reporting correctly.
