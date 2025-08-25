
# Micro-01: Ansible – VLAN + Access Port (Cisco IOS)

Configures VLANs + access ports (mode access + access VLAN) + description via `cisco.ios`. Idempotent.

## Quick start
```bash
ansible-galaxy collection install cisco.ios ansible.netcommon
export ANSIBLE_NET_USERNAME=admin
export ANSIBLE_NET_PASSWORD='P@ssw0rd!'
ansible-playbook -i inventory/hosts.yml playbook.yml --check --diff
ansible-playbook -i inventory/hosts.yml playbook.yml
```

## Variables (`host_vars/lab-switch.yml`)
```yaml
vlans:
  - { id: 10, name: USERS, state: present }
  - { id: 99, name: NATIVE, state: present }

access_ports:
  - { name: GigabitEthernet1/0/1, vlan: 10, description: "Office-101 PC" }
  - { name: GigabitEthernet1/0/2, vlan: 10, description: "Spare" }
```
