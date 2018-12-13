# LGSM

Installs and configures [LinuxGSM](https://linuxgsm.com/) servers.

## Role Variables

```yaml
# LGSM server name (game name). REQUIRED
lgsm_server_name: ""
# LGSM server file name (used for executing commands). REQUIRED
lgsm_server_file_name: ""
# LGSM server group name
lgsm_server_group: "lgsm"
# LGSM server user name
lgsm_server_user: "lgsm"
# LGSM server config configuration
lgsm_server_common_config: ""
# LGSM server specific configuration
lgsm_server_specific_config: ""
# LGSM commands to run after initialization of the server file
lgsm_server_commands:
  - "auto-install"
  - "start"
  - "details"
  - "stop"
# LGSM dependencies to install
lgsm_dependencies:
  - mailutils
  - postfix
  - curl
  - wget
  - file
  - bzip2
  - gzip
  - unzip
  - bsdmainutils
  - python
  - util-linux
  - ca-certificates
  - binutils
  - bc
  - jq
  - tmux
  - lib32gcc1
  - libstdc++6
  - libstdc++6:i386
```

NOTE: The Ansible user needs to be able to become `lgsm_server_user` from `lgsm_server_group`.

## Example Playbook

Creates a Killing Floor 2 server as `/home/lgsm/kf2-mainserver`.

    - hosts: lgsm-servers
      roles:
         - { role: lgsm, lgsm_server_name:'kf2server', lgsm_server_file_name: 'kf2-mainserver' }

## License

MIT

## Author Information

This role was created in 2018 by Ruben Harutyunyan.
