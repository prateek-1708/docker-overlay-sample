Vagrant.configure(2) do |config|
  
   config.vm.define "dkr_host_1" do |dkr_host_1|
    dkr_host_1.vm.box = "centos/7"
    dkr_host_1.vm.hostname = 'dkr-host-1'
    dkr_host_1.vm.network :private_network, ip: "192.168.56.101"
    dkr_host_1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "dkr_host_1"]
    end
    dkr_host_1.vm.synced_folder ".", "/home/vagrant/sync", disabled: true
    dkr_host_1.vm.synced_folder "./host_1", "/vagrant"
  end

  config.vm.define "dkr_host_2" do |dkr_host_2|
    dkr_host_2.vm.box = "centos/7"
    dkr_host_2.vm.hostname = 'dkr-host-2'
    dkr_host_2.vm.network :private_network, ip: "192.168.56.102"

    dkr_host_2.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "dkr_host_2"]
    end
    dkr_host_2.vm.synced_folder ".", "/home/vagrant/sync", disabled: true
    dkr_host_2.vm.synced_folder "./host_2", "/vagrant"
  end

   config.vm.define "dkr_host_3" do |dkr_host_3|
    dkr_host_3.vm.box = "centos/7"
    dkr_host_3.vm.hostname = 'dkr-host-3'
    dkr_host_3.vm.network :private_network, ip: "192.168.56.103"

    dkr_host_3.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "dkr_host_3"]
    end
    dkr_host_3.vm.synced_folder ".", "/home/vagrant/sync", disabled: true
    dkr_host_3.vm.synced_folder "./host_3", "/vagrant"
  end

end
