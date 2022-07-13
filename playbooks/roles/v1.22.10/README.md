# Ansible playbook to install k8s cluster version 1.22.10

Available for version >= 1.21.0

Command:

```bash
ANSIBLE_CONFIG=demo.cfg ansible-playbook playbooks/k8s_acb_demo.yml -vv \
--become --become-user=root --become-method=sudo -e ansible_ssh_user=ec2-user \
-e ansible_ssh_private_key_file=~/acb-dev.pem
```

Something need to config:
- host in inventory [k8s.yml](../../../inventory/demo/k8s.yml)
- k8s-master-advertise-address in role master [main.yml](master/defaults/main.yml)