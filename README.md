# Ansible script to install k8s cluster

Only apply for RHEL7 Node
## Ansible playbook to install k8s cluster version 1.22.10

Command:

```bash
ANSIBLE_CONFIG=demo.cfg ansible-playbook playbooks/k8s-1.22.10.yml -vv \
--become --become-user=root --become-method=sudo -e ansible_ssh_user=ec2-user \
-e ansible_ssh_private_key_file=~/demo.pem
```

Something need to config:
- host in inventory [k8s.yml](../../../inventory/demo/k8s.yml)
- k8s-master-advertise-address in role master [main.yml](master/defaults/main.yml)


## Ansible playbook to install k8s cluster version 1.16.10

Command:

```bash
ANSIBLE_CONFIG=demo.cfg ansible-playbook playbooks/k8s-1.16.10.yml -vv \
--become --become-user=root --become-method=sudo -e ansible_ssh_user=ec2-user \
-e ansible_ssh_private_key_file=~/demo.pem
```

Something need to config:
- host in inventory [k8s.yml](../../../inventory/demo/k8s.yml)
- k8s-master-advertise-address in role master [main.yml](master/defaults/main.yml)


### Compare with v1.22.10

- Do not need to install docker and kube* packages
- AMI (AWS) installed docker, kube* v1.16.10