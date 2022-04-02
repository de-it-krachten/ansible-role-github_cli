[![CI](https://github.com/de-it-krachten/ansible-role-github_cli/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-github_cli/actions?query=workflow%3ACI)


# ansible-role-github_cli

Installs the github cli on Linux systems

Platforms
--------------

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- AlmaLinux 8<sup>1</sup>
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

Role Variables
--------------
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


Example Playbook
----------------

<pre><code>
- name: sample playbook for role 'github_cli'
  hosts: all
  vars:
  tasks:
    - name: Include role 'github_cli'
      include_role:
        name: github_cli
</pre></code>
