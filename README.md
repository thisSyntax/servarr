# servarr

## .env
The .env file contains the the configuration options for PUID and PGID for the Arr apps as well as the VPN configuration variable for Gluetun, I use ProtonVPN at the moment  so the information below is what used based on the [Gluetun wiki](https://github.com/qdm12/gluetun-wiki/blob/main/setup/providers/protonvpn.md)

## Required environment variables

- `VPN_SERVICE_PROVIDER=protonvpn`

### Wireguard only

- `VPN_TYPE=wireguard`
- `WIREGUARD_PRIVATE_KEY` is your 32 byte key in base64 format. The private key can be obtained by [generating a Wireguard configuration file](https://account.proton.me/u/0/vpn/WireGuard) and copy the displayed `PrivateKey` value. Note this value works for all ProtonVPN servers. 💁 [Guide on how to generate a configuration file](https://protonvpn.com/support/wireguard-configurations/)
 - `WIREGUARD_ADDRESSES` is the Wireguard IP network interface address in CIDR format `xx.xx.xx.xx/xx`. To obtain it, first download a Wireguard configuration file using same steps as for `WIREGUARD_PRIVATE_KEY` above. In the configuration file, locate the `Address` value. This one should contain a comma delimited list of an IPv4 and IPv6 address, so use the IPv4 address (usually the first one) as the value for the `WIREGUARD_ADDRESSES` environment variable. Note this is the same value for all Mullvad servers and for your private key. 💁 [Screenshots on how to obtain it](https://github.com/qdm12/gluetun/discussions/805#discussioncomment-2026642).

 ## Optional environment variables

- `SERVER_COUNTRIES`: Comma separated list of countries