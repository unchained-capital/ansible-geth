# ansible-geth

This role has been adapted somewhat from the upstream version.

Playbooks for setting up geth nodes for main net and Ropsten

## Install

Clone the role into your geth configuration.

    git clone https://github.com/mikeshultz/ansible-geth.git /etc/ansible/roles/geth

Create a role for your machine that inherits from this one to change the default
options.

    ---
    - hosts: ropsten
      become: yes
      become_method: sudo
      vars:
        geth_testnet: true
        geth_cache: 512
        geth_port: 30304
        geth_datadir: /data/ropsten
        geth_rpc: true
        geth_rpcpublic: true
        geth_rpcaddr: 0.0.0.0
        geth_rpcport: 8080
      roles:
        - geth

