# -*- mode: ruby -*-
# vi: set ft=ruby :

V_CPU = 1 # in cores
V_MEM = 1024 # in megabytes per core
V_NAME = 'monitor' 

Vagrant.configure("2") do |config|
  
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
    end

    config.vm.box = "ubuntu/focal64"
	
	config.vm.network "forwarded_port", guest: 80, host: 8081
    # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
	config.vm.network "private_network", ip: "192.168.19.123"
    # config.vm.network "public_network"
    config.vm.synced_folder ".", "/vagrant", disabled: true

    # Provider-specific configuration so you can fine-tune various
    # backing providers for Vagrant. These expose provider-specific options.
    # Example for VirtualBox:
    #
    # config.vm.provider "virtualbox" do |vb|
    #   # Display the VirtualBox GUI when booting the machine
    #   vb.gui = true
    #
    #   # Customize the amount of memory on the VM:
    #   vb.memory = "1024"
    # end
    config.vm.provider "virtualbox" do |v|
    
      v.memory = V_MEM
      v.name = V_NAME
      v.cpus = V_CPU
	 
    end

end
