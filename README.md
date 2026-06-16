# About
This repository contains the infrastructure for my personal VPN setup.

It is intended to be used with two tunnels:
- WireGuard
- VLESS + Reality + Vision (self-stealing)

# Installation
## 3x-ui
Since 3x-ui does not support unattended installation, it must be configured manually.

Uncomment the `2053` port mapping in `3x-ui/compose.yml`, then configure the following settings through that port:
- Reality tunnel with self-stealing from `traefik:443`
- Panel URI path: `/3x-ui/`
- Subscription URI path: `/3x-ui-sub/` (and the corresponding Reverse Proxy URI)

Once done, do not forget to comment port mapping again.

## wg-easy
Create `wg-easy/wg-easy.env` using `wg-easy/wg-easy.env.example` as a template.

# Caveats
Keep in mind that the setup relies on the `$HOSTNAME` environment variable. If it is not provided by your environment, define it in each of the following files:
- `3x-ui/.env`
- `wg-easy/.env`

