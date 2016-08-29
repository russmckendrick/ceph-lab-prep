Ceph Lab Prep
====================

This set of Ansible scripts prepares three hosts, it assumes;

- You are using Ansible 2.1 and above
- You have three Ubuntu 14.04 hosts
- You have a user with an SSH key on all three hosts
- You have both a public (eth0) & private (eth1) networking on each of the hosts

To use these playbooks you should create you own hosts file by running the following command;

```
cp -pr hosts_example hosts
```

and then update the IP addresses to be those of your three hosts, once you have done that you should be able to run ...

```
ansible-playbook -i hosts prep.yml
```

Please note, this playbook does not install or configure Ceph, it only ...

- Installs & starts NTP on all hosts
- Updates the hostname of all hosts
- Updates the `hosts` file on all hosts using the hostname and the IP address assigned to eth1
- Creates a user called `cephdeploy` user on each host
- Exchanges keys between all hosts
- Adds the Ceph repo on all hosts
- Installs `ceph-deploy` on one of the hosts

[![asciicast](https://asciinema.org/a/84177.png)](https://asciinema.org/a/84177)