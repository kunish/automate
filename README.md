# Using ansible playbook to manage my homelab servers

## How to use

### Write a inventory file or copy the inventory/example.yml and make it your own

```bash
cp inventory/example.yml inventory/main.yml
```

or

```bash
cat > inventory/main.yml << EOF
remote:
  hosts:
    cloud-vm:
      ansible_user: ubuntu
      ansible_port: 10022
      ansible_ssh_private_key_file: ~/.ssh/cloud-vm.key
homelab:
  hosts:
    workstation:
    gateway:
EOF
```

### deploy

```bash
ansible-playbook -i inventory/main.yml main.yml
```
