# Shadowsocks Server Provision Tool

The automation script for provision a new shadowsocks server.

Will provision a new [ShadowSocks](https://shadowsocks.org/):

- [ShadowSocks Server (python implementation)](https://github.com/shadowsocks/shadowsocks/tree/master), using manage mode (so that we can use the manager service)
- [ShadowSocks Manager](https://github.com/shadowsocks/shadowsocks-manager), for manage the service
- [ShadowSocks Manager Web Plugin (the Web Interface)](https://github.com/shadowsocks/shadowsocks-manager/blob/master/plugins/webgui/README.md)


## Requirements

- Local machine:
    - Python
    - virtualenv
- Server:
    - Ubuntu 16.04 or 14.04


## How to use

1. clone this repo: `git clone git@github.com:winguse/ss_server_provision.git`
2. enter the repo: `cd ss_server_provision` 
3. setup virtual env: `virtualenv env` and `source env/bin/activate`
4. install dependencies: `pip install -r requirements`
5. modify `./group_vars/vpn/config` to your config
6. modify `./production` for your machines
7. run `./run.sh`
8. login to the server, run `letsencrypt certonly` to obtain a free SSL cert for the Web UI
9. visit the Web UI for config

WARNING: for credential, please use `ansible-vault` instead of `./group_vars/vpn/config`. I am only to provide a simple example here.
