# Nginx Ansible Role

This Ansible role installs and configures Nginx on target hosts, along with deploying a basic index.html file.

## Installation

To use this role, you need to have Ansible installed on your control node. You can install it via the Ansible PPA repository:

```bash
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible
```

## Usage

1. Clone or download this repository to your Ansible control node.

2. Create a directory structure for your playbook:

```
nginx_deploy/
├── roles/
│   └── nginx/
│       ├── tasks/
│       │   └── main.yml
│       └── files/
│           └── index.html
├── playbook.yml
└── inventory
```
OR

```
ansible-galaxy init nginx
```

3. Write your playbook (`playbook.yml`) with the following content:

```yaml
---
- name: Install and configure Nginx
  hosts: your_ubuntu_servers
  become: true

  roles:
    - nginx
```

Replace `your_ubuntu_servers` with your actual inventory group or host.

4. Ensure that the `nginx` role is moved to the `/etc/ansible/roles` directory:

```bash
sudo mv roles/nginx /etc/ansible/roles
```

5. Run your playbook:

```bash
ansible-playbook -i inventory playbook.yml
```

## Contributing

If you encounter any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
