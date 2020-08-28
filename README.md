# ConfManWS

Use Ansible to configure a simple web server.

## Useful commands
```sh
ansible-playbook main.yml
```

## To modify in the hosts file
```
[ansimaster]
192.168.0.17 ansible_connection=local

[ansislave]
192.168.0.18 ansible_ssh_pass=vagrant ansible_ssh_user=vagrant
```

## Some playbook tasks
```yml
- name: Install the package "foo"
    become: true
    apt:
      name: foo
- name: Copy file with owner and permissions
  copy:
    src: /srv/myfiles/foo.conf
    dest: /etc/foo.conf
    owner: foo
    group: foo
    mode: '0644'
```
