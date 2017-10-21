# Ansible-role-squid

**Version: 0.1.0**

 - Requires Ansible 2.0+
 - Compatible with most versions of RHEL/CentOS 6.x, 7.x

## Installation

### Directly from ansible-galaxy (latest release)
```bash
$ ansible-galaxy install marcinpraczko.squid
```

### Directly from github repository

Sometimes some changes has been applied to ``develop`` or ``feature`` branch and are not yet released.
Ansible-galaxy allows install roles directly from ``GitHub``.

```bash
mkdir testing-roles
cd testing-roles
ansible-galaxy install -p roles git+https://github.com/marcinpraczko/ansible-role-named.git,develop
```

Above example will install ``develop`` branch. This can be adjusted to any git SHA commit, tag or branch
name - depends of requirements.

Checking what version is installed can be done with command:
```bash
ansible-galaxy list -p roles
```

## Getting started

### Installing Squid

Installing ``squid`` and all required dependencies is very simple and can be done before configuration 
or individually on it's own: 

#### Install Only

```bash
$ ansible-playbook -t install -i hosts squid.yml
```

#### Run the Whole Playbook

```bash
$ ansible-playbook -i hosts squid.yml
```

### Example Playbook, Hosts, and Group Variables

#### Example Playbook

```yaml
- name: "Actions Needed to Get Masters Into a Happy State"
  hosts: squid_servers
  remote_user: root

  roles:
    - "marcinpraczko.squid"

#### Example Hosts

```ini
[squid_servers]
127.0.0.1
```

