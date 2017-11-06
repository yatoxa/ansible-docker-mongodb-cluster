# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "ci_3350" do |ci_3350|
    ci_3350.vm.box = "centos/7"
    ci_3350.vm.box_check_update = false
    ci_3350.vm.hostname = "ci-3350"
    ci_3350.vm.network "private_network", ip: "192.168.33.50"
    ci_3350.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = "512"
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "90"]
    end
  end

  config.vm.define "dev_ms01_3351" do |dms01_3351|
    dms01_3351.vm.box = "centos/7"
    dms01_3351.vm.box_check_update = false
    dms01_3351.vm.hostname = "dms01-3351"
    dms01_3351.vm.network "private_network", ip: "192.168.33.51"
    dms01_3351.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = "512"
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "90"]
    end
  end

  config.vm.define "dev_ms02_3352" do |dms02_3352|
    dms02_3352.vm.box = "centos/7"
    dms02_3352.vm.box_check_update = false
    dms02_3352.vm.hostname = "dms02-3352"
    dms02_3352.vm.network "private_network", ip: "192.168.33.52"
    dms02_3352.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = "512"
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "90"]
    end
  end

  config.vm.define "dev_ms03_3353" do |dms03_3353|
    dms03_3353.vm.box = "centos/7"
    dms03_3353.vm.box_check_update = false
    dms03_3353.vm.hostname = "dms03-3353"
    dms03_3353.vm.network "private_network", ip: "192.168.33.53"
    dms03_3353.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = "512"
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "90"]
    end
  end

  config.vm.provision "shell" do |s|
    ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
    s.inline = <<-SHELL
      if [ ! -f ~/runonce ]
        then
          echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
          touch ~/runonce
      fi
      yum -y update
      yum -y install vim
    SHELL
  end

end
