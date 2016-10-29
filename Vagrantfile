# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "nfs01" do |v|
    v.vm.hostname = "nfs01"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.200"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 512]
      p.customize ["modifyvm", :id, "--name", "nfs01"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 1
    end

    v.vm.provision "ansible" do |ansible|
      ansible.playbook = "nfs.yaml"
      ansible.inventory_path = "./hosts"
      ansible.limit = "nfs"
    end
  end

  config.vm.define "http01" do |v|
    v.vm.hostname = "http01"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.201"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 512]
      p.customize ["modifyvm", :id, "--name", "http01"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 1
    end

    v.vm.provision "ansible" do |ansible|
      ansible.playbook = "http.yaml"
      ansible.inventory_path = "./hosts"
      ansible.limit = "http01"
    end
  end

  config.vm.define "http02" do |v|
    v.vm.hostname = "http02"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.202"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 512]
      p.customize ["modifyvm", :id, "--name", "http02"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 1
    end

    v.vm.provision "ansible" do |ansible|
      ansible.playbook = "http.yaml"
      ansible.inventory_path = "./hosts"
      ansible.limit = "http02"
    end
  end

  config.vm.define "hp01" do |v|
    v.vm.hostname = "hp01"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.203"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 256]
      p.customize ["modifyvm", :id, "--name", "hp01"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 1
    end

    v.vm.provision "ansible" do |ansible|
      ansible.playbook = "haproxy.yaml"
      ansible.inventory_path = "./hosts"
      ansible.limit = "hp01"
    end
  end

  config.vm.define "hp02" do |v|
    v.vm.hostname = "hp02"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.204"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 256]
      p.customize ["modifyvm", :id, "--name", "hp02"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 1
    end

    v.vm.provision "ansible" do |ansible|
      ansible.playbook = "haproxy.yaml"
      ansible.inventory_path = "./hosts"
      ansible.limit = "hp02"
    end
  end

  config.vm.define "db01", primary: true do |v|
    v.vm.hostname = "db01"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.205"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 512]
      p.customize ["modifyvm", :id, "--name", "db01"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 2
    end

    v.vm.provision "ansible" do |ansible|
      ansible.playbook = "sql.yaml"
      ansible.inventory_path = "./hosts"
      ansible.limit = "db01"
    end
  end

  config.vm.define "db02" do |v|
    v.vm.hostname = "db02"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.206"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 512]
      p.customize ["modifyvm", :id, "--name", "db02"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 2
    end

    v.vm.provision "ansible" do |ansible|
      ansible.playbook = "sql.yaml"
      ansible.inventory_path = "./hosts"
      ansible.limit = "db02"
    end
  end
end
