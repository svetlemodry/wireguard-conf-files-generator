# Ansible wireguard configuration files generator

I need to deploy new wireguard configurations for family and friends
from time to time. Getting the configuration files created manualy is
time consuming, so I wrote this ansible playbook to speed things up.

It generates two formats of wireguard "server" conf files. One is for a regular
wireguard [VPN server](https://wiki.archlinux.org/title/WireGuard#Server) and the
other can be used in a Homeassistant [wireguard addon](https://github.com/hassio-addons/addon-wireguard).

Peer configuration files along with a QR code PNG file that can be scanned
with a smartphone for easy setup are saved in separate subdirectories.

The playbook uses `wg` and `qrencode` commands to generate all the conf files,
so those need to be available prior running the `ansible-playbook`.

USAGE:
* clone the git repository
* edit the variables in the `wireguard-config-create.yml` file as you need
* run the playbook with `ansible-playbook wireguard-config-create.yml`
