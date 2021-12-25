
## Initial Ubuntu server config done through Ansible.

Tested on fresh Ubuntu 20.04 LTS with root account SSH access.

Create user for Ansible with key based authentication and sudo privileges:
```shell
ansible-playbook setup_ansible_user.yml --ask-pass
```

Upgrade all packages and restart server if necessary:
```shell
ansible-playbook initial_upgrade.yml
```

Secure SSH - disable root login and password authentication:
```shell
ansible-playbook secure_ssh.yml
```

Install Docker, Docker Compose and add user to group docker:
```shell
ansible-playbook install_docker.yml
```