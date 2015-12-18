[ansible](http://www.ansible.com) playbook for setting up development environment on centos7

Before execute playbooks, you need to setup hosts file in "/etc/ansible/hosts".(if OSX its in "/usr/local/etc/ansible/hosts")

You can use openssh(with ssh-config option) rather than default python ssh libs.

```
[servers]
vagrant  ansible_connection=ssh
```

You can check connections health with 'ping' command.

```
> ansible all -m ping
vagrant | success >> {
    "changed": false,
    "ping": "pong"
}

> ansible vagrant -a "/bin/date"
vagrant | success | rc=0 >>
Fri Dec 18 07:36:07 UTC 2015
```

