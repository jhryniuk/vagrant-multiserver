Vagrant Multi Server
====================
## Description:

### Ansible roles which provide:
* Nfs server as shared space for rest servers, nfs01 - IP = `10.0.0.200`
* Two mysql servers with InnoDb or MariaDb engine
    * db01 - master, IP = `10.0.0.201`
    * db02 - slave, IP = `10.0.0.202`
    
Those two servers are connected by replication `master - slave`

* Server with php5-fpm and nginx, http01 - IP = `10.0.0.203`


### Requirements:

* [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads.html)

### How to run this machine?

* Download from git repository `https://github.com/jhryniuk/vagrant-multiserver.git`
* Get inside vagrant folder
* In file `vars/db.yml` uncomment correct version of db engine
* Run command `vagrant up`

### How to shut down this machine?

In order to turn off virtual machine run command `vagrant halt`

### Current known issues:

* After `vagrant up` database servers are not correct replicated
In order to finish replication process you need to run command `vagrant provision db01 db02`

### Bugs

Any issues, suggestions please leave here [Issues](https://github.com/jhryniuk/vagrant-multiserver/issues)