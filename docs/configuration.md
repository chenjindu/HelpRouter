# Configuration

Everything is configured from the web UI at **http://192.168.8.1**
(reachable from any device connected to the HelpRouter hotspot).
A built-in web terminal is available for anything beyond the UI — and full SSH access is included.

<!-- TODO(维护提示): 本文按产品功能编写；界面菜单名称如与实际 Web UI 不一致，请按实际界面微调。 -->

<p align="center">
  <img src="images/webui-dashboard.png" alt="Web UI dashboard" width="720">
</p>

## WAN — the upstream connection

Three ways to get HelpRouter online:

- **WiFi repeater** — scan and join any upstream WiFi (hotel, Airbnb, office). The upstream
  credentials are stored per-network, so returning to a known location reconnects automatically.
- **Wired Ethernet** — plug into the Gigabit port; useful where wired is offered or WiFi is poor.
- **MAC clone** — on networks that only allow one registered device, clone the MAC of a device
  that's already been admitted. All your devices then share that single admission.

A connection watchdog re-establishes dropped upstream WiFi automatically — no manual intervention
when the hotel AP hiccups at 3 a.m.

## LAN & Hotspot

- **Dual-band hotspot** — separate 2.4 GHz and 5 GHz networks; set SSIDs and passwords
  independently. Change the defaults on first boot.
- **Fixed IPs** — assign each device a permanent IP (DHCP reservation). Your SSH configs,
  bookmarks and scripts keep working forever, wherever the router travels.
- **LAN subnet** — defaults to `192.168.8.0/24` with the router at `192.168.8.1`; adjustable
  if it collides with an upstream network.

## DNS Filtering

Network-level filtering applied to every device automatically — nothing to install on clients:

- **Ad blocking** — block ad domains at resolution time
- **Malware & phishing protection** — block known malicious domains
- **Adult content filtering** — family-safe mode with one toggle

Each category is an independent switch. Custom allow/deny lists are supported for
domains you want to force through or force out.

## VPN

- **VPN server** (WireGuard & OpenVPN) — reach your home LAN securely from anywhere;
  client configs are generated from the UI, scan-to-import for phones.
- **VPN client** — route all LAN traffic through your VPN provider; every device
  behind HelpRouter is covered without per-device setup.

## Remote Access

1. Pick your free subdomain — `yourname.hc.ink`
2. Flip the switch

That's the whole setup. Behind a public IP the DDNS path is used; behind NAT/CGNAT the
built-in tunnel keeps you reachable. No port forwarding, ever.

## Built-in Services

Toggle each service on/off from the UI:

| Service | What it's for |
|---|---|
| SSH | Remote shell access to the router itself |
| SMB | Windows/Mac network file sharing |
| FTP | Classic file transfer |
| Git | Host private repositories on your own hardware |
| SVN | Subversion version control |
| DNS | The filtering resolver (see above) |
| Web | Host static sites on your LAN |
| File | HTTP file server with a browser UI |
| Local Share | Drop-in text & file sharing page between devices — no app, no cloud |

## System

- **Upgrade** — the system checks for updates; upgrading is one click.
- **Backup & restore** — export the full configuration to a file; restore it onto a fresh
  flash to clone or recover your setup in minutes.
- **Web terminal** — a real shell in the browser, for when you want to go under the hood.
- **Logs** — system and connection logs viewable from the UI for troubleshooting.

## Default Credentials (change these!)

| What | Default |
|---|---|
| Hotspot SSID | `HelpRouter` |
| Hotspot password | `helprouter` |
| Web UI | `http://192.168.8.1` — admin password set during the wizard |

The setup wizard walks you through changing all of these on first boot.
