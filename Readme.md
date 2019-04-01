### Sample symfony app deployment with ansible
This repo shows how to deploy symfony applicaton on ubuntu 18. Virtual machine for deployment are created
using Vagrant.

#### Prerequisites

* Ansible v. 2.6 and above
* Libvirt (as virtualization engine). VirtualBox can be used instead but this setup isn't tested yet
* Vagrant v. 2.1 and above with [libvirt support enabled](https://github.com/vagrant-libvirt/vagrant-libvirt).

### Usage

1. Create virtual machine:

```
vagrant up --provider libvirt
```

2. Run ansible to setup VM and deploy symfony application:

```
ansible-playbook site.yml
```

3. Verify that application is deployed by navigating to http://10.20.30.40 in your browser.


### Continuous deployment

This is possible to redeploy multiple times by running:

```
ansible-playbook site.yml
```

Also you can save time by running only deploy tasks:

```
ansible-playbook site.yml -t deploy
```
