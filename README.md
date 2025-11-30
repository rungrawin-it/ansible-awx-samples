# ansible-awx-samples

A collection of sample Ansible playbooks designed for use with AWX/Ansible Tower. These helper playbooks can be used to test connectivity, identify issues, and run basic diagnostics on target hosts.

## Playbooks

### ping.yml
Tests connectivity to target hosts using the Ansible ping module.

```bash
ansible-playbook playbooks/ping.yml -i inventory
```

### whoami.yml
Identifies the user running commands on target hosts.

```bash
ansible-playbook playbooks/whoami.yml -i inventory
```

### get_hostname.yml
Retrieves the hostname of target machines.

```bash
ansible-playbook playbooks/get_hostname.yml -i inventory
```

### delay.yml
Runs a delay/sleep task for a specified number of seconds. Default is 10 seconds. Useful for testing long-running tasks.

```bash
# Default delay (10 seconds)
ansible-playbook playbooks/delay.yml -i inventory

# Custom delay (e.g., 30 seconds)
ansible-playbook playbooks/delay.yml -i inventory -e "delay_seconds=30"
```

## Usage with AWX

1. Add this repository as a Project in AWX
2. Create Job Templates for each playbook
3. Run the Job Templates against your inventories to test connectivity and diagnose issues

## Requirements

- Ansible Core 2.9+
- AWX or Ansible Tower (for AWX integration)