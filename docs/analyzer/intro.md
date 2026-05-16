# Analyzer & MQTT Packet Broker

MeshCore observers capture mesh traffic and publish it to MQTT brokers, feeding telemetry dashboards, maps, and packet inspectors. This section covers the four ways to connect an observer to the MeshCore.ca broker pair.

## MeshCore.ca Brokers

All observer paths connect to the same two brokers for redundancy:

| Broker | Host | Port | Transport |
|--------|------|------|-----------|
| Primary | `mqtt1.meshcore.ca` | 443 | WebSockets (TLS) |
| Backup | `mqtt2.meshcore.ca` | 443 | WebSockets (TLS) |

Both use JWT token authentication and TLS verification. No username or password is needed.

## Choose Your Observer Path

Pick the setup that matches your hardware and environment:

| Path | Best For | Guide |
|------|----------|-------|
| **MQTT Firmware** | Standalone devices with WiFi (e.g. Heltec V3). No host computer needed. | [MQTT Firmware](builds/mqtt-firmware.md) |
| **MCtoMQTT (USB Host)** | Repeaters or room servers connected to a Linux/macOS host via USB serial. Also covers companion radios via BLE/serial/TCP. | [MCtoMQTT Script](builds/mctomqtt.md) |
| **PyMC** | Python-based repeater setups using the pyMC library. | [PyMC](builds/pymc.md) |
| **Home Assistant** | HA users with the MeshCore integration who want mesh telemetry in their dashboards. | [MeshCore-HA](builds/meshcore-ha.md) |

## IATA Region Codes

Each observer identifies its region with a 3-character IATA code. Use the airport code nearest to your location. The following codes are supported on [live.meshcore.ca](https://live.meshcore.ca) today.

??? note "Ontario"

    | Code | Region |
    |------|--------|
    | YYZ | Toronto (Pearson) |
    | YTZ | Toronto (Billy Bishop) |
    | YOW | Ottawa |
    | YHM | Hamilton |
    | YKF | Kitchener / Waterloo |
    | YXU | London |
    | YOO | Oshawa |
    | YKZ | Buttonville / Markham |
    | YAM | Sault Ste. Marie |
    | YQT | Thunder Bay |
    | YSB | Sudbury |
    | YTS | Timmins |
    | YQG | Windsor |
    | YYB | North Bay |
    | YGK | Kingston |
    | YPQ | Peterborough |
    | YHD | Dryden |
    | YPL | Pickle Lake |
    | YND | Gatineau (Ottawa area) |

??? note "Quebec"

    | Code | Region |
    |------|--------|
    | YUL | Montreal (Trudeau) |
    | YMX | Montreal (Mirabel) |
    | YQB | Quebec City |
    | YBG | Bagotville / Saguenay |
    | YVO | Val-d'Or |
    | YHU | Montreal (St-Hubert) |
    | YRJ | Roberval |
    | YGL | La Grande Rivière |
    | YSC | Sherbrooke |
    | YTQ | Tasiujaq |
    | YUY | Rouyn-Noranda |
    | YZV | Sept-Îles |
    | YGP | Gaspé |
    | YRQ | Trois-Rivières |

??? note "British Columbia"

    | Code | Region |
    |------|--------|
    | YVR | Vancouver |
    | YYJ | Victoria |
    | YXX | Abbotsford / Fraser Valley |
    | YLW | Kelowna |
    | YXS | Prince George |
    | YPR | Prince Rupert |
    | YXT | Terrace |
    | YQQ | Comox / Courtenay |
    | YCD | Nanaimo |
    | YYD | Smithers |
    | YDQ | Dawson Creek |
    | YXJ | Fort St. John |
    | YYF | Penticton |
    | YCG | Castlegar |
    | YKA | Kamloops |
    | YXC | Cranbrook |
    | YBC | Baie-Comeau |

??? note "Alberta"

    | Code | Region |
    |------|--------|
    | YYC | Calgary |
    | YEG | Edmonton |
    | YMM | Fort McMurray |
    | YQU | Grande Prairie |
    | YQL | Lethbridge |
    | YXH | Medicine Hat |

??? note "Saskatchewan"

    | Code | Region |
    |------|--------|
    | YQR | Regina |
    | YXE | Saskatoon |
    | YPA | Prince Albert |

??? note "Manitoba"

    | Code | Region |
    |------|--------|
    | YWG | Winnipeg |
    | YBR | Brandon |
    | YTH | Thompson |
    | YDN | Dauphin |
    | YPG | Portage la Prairie |

??? note "New Brunswick"

    | Code | Region |
    |------|--------|
    | YFC | Fredericton |
    | YSJ | Saint John |
    | YQM | Moncton |
    | ZBF | Bathurst |

??? note "Nova Scotia"

    | Code | Region |
    |------|--------|
    | YHZ | Halifax |
    | YQY | Sydney |
    | YQI | Yarmouth |

??? note "Prince Edward Island"

    | Code | Region |
    |------|--------|
    | YYG | Charlottetown |

??? note "Newfoundland and Labrador"

    | Code | Region |
    |------|--------|
    | YYT | St. John's |
    | YQX | Gander |
    | YDF | Deer Lake |
    | YYR | Goose Bay |
    | YWK | Wabush |

??? note "Territories (YT / NT / NU)"

    | Code | Region |
    |------|--------|
    | YXY | Whitehorse (Yukon) |
    | YZF | Yellowknife (NWT) |
    | YFB | Iqaluit (Nunavut) |
    | YEV | Inuvik (NWT) |
    | YHY | Hay River (NWT) |

## Verify Your Observer

After setting up any observer path, head to [Verify Observer Status](verify.md) to confirm it's online and reporting correctly.
