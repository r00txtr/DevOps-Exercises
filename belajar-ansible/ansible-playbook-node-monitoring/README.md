# ansible-playbook-node-monitoring
Hosts are provisioned with vagrant (virtualbox)
For learning purpose

### Prerequisite
- Ansible
- Vagrant

#### Vagrant setup
```
vagrant up
```

#### Create symlink
```
ln -s ../roles playbooks/roles
```
##### Generate SSH Key
```
ssh-keygen -t rsa -b 4096 -C "vagrant-key" -f $PWD/key/vagrant-key
```
