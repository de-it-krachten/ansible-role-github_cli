[![CI](https://github.com/de-it-krachten/ansible-role-github_cli/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-github_cli/actions?query=workflow%3ACI)


# ansible-role-github_cli

Installs the github cli on Linux systems


## Dependencies

#### Roles
None

#### Collections
- community.general
- ansible.posix

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 10 (Buster)<sup>1</sup>
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 37
- Fedora 38

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Github CLI - API
github_cli_api: https://api.github.com/repos/cli/cli

# Github CLI - repo
github_cli_repo: https://github.com/cli/cli

# Lookup table for architecture
github_cli:
  architecture:
    x86: 386
    x86_64: amd64
  system:
    Linux: linux
    Darwin: MacOS
    windows: windows

# Should the cli be downloaded
github_cli_download: true

# Version of the CLI to install
github_cli_version: latest

# Location/ownership/permissions of the binary
github_cli_path: /usr/bin/gh
github_cli_owner: root
github_cli_group: root
github_cli_mode: '0755'
</pre></code>


### vars/main.yml
<pre><code>
github_cli:
  architecture:
    x86: 386
    x86_64: amd64
  system:
    Linux: linux
    Darwin: MacOS
    windows: windows
</pre></code>



## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'github_cli'
  hosts: all
  become: "yes"
  tasks:
    - name: Include role 'github_cli'
      ansible.builtin.include_role:
        name: github_cli
</pre></code>
