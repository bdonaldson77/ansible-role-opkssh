opkssh
=========

A simple role to install [opkssh](https://github.com/openpubkey/opkssh) on a linux machine and configure it as an SSH auth source.

This repo is not affiliated with opkssh or its original authors, I just wanted to write it to install opkssh on my homelab.

Requirements
------------

See [requirements.yaml](./requirements.yml) for required collections.

Supported Platforms
-------------------

### Server support

| OS           | Supported | Tested | Version Tested       | 
| --           | --------- | ------ | --------------       | 
| Ubuntu x86   | ✅        | ✅     |  Ubuntu 22.04.5 LTS  |
| Ubuntu arm64 | ✅        | ✅     |  Ubuntu 22.04.5 LTS  |

Role Variables
--------------

`setup_home_policy`: Whether or not to allow opkssh see policy files in user's home directory. Default: `true`

`auth_cmd_user`: User to be created to run opkssh and do the AuthorizedKeysCommandUser lookup with. Default: `opksshuser`

`auth_cmd_group`: Group to add the `auth_cmd_user` to. This group owns all the config files and directories opkssh needs. Default: `opksshuser`

`opkssh_version`: Version of opkssh to install. When set to `latest`, this role will check the opkssh GitHub repo for the latest release and use that version. Default: `latest`

`opkssh_arch`: The platform architecture for downloading the relevant opkssh executable. Default: `amd64`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: bdonaldson77.opkssh, opkssh_arch: 'arm64' }

License
-------

Apache 2.0

