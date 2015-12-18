[ansible](http://www.ansible.com) playbook for setting up development environment on centos7

Before execute playbooks, you need to setup hosts file in "/etc/ansible/hosts".(if OSX its in "/usr/local/etc/ansible/hosts")

You can use openssh rather than default python ssh libs.

```
[servers]
vagrant  ansible_connection=ssh
azuki.cc ansible_connection=ssh
```

You can check connections with 'ping' command.

```
> ansible all -m ping
vagrant | success >> {
    "changed": false,
    "ping": "pong"
}

azuki.cc | success >> {
    "changed": false,
    "ping": "pong"
}

> ansible vagrant -a "/bin/date"
vagrant | success | rc=0 >>
Fri Dec 18 07:36:07 UTC 2015

> ansible azuki.cc -a "/bin/date"
azuki.cc | success | rc=0 >>
Fri Dec 18 16:33:47 JST 2015
```

