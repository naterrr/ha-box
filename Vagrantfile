# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "Ubuntu-13.10-64"
  config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/saucy/current/saucy-server-cloudimg-amd64-vagrant-disk1.box"

  config.vm.network :private_network, ip: "10.0.54.60"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end
  
  # config.vm.provider :aws do |aws, override|
  #   config.vm.box = "dummy"
  #   
  #   aws.access_key_id = ""
  #   aws.secret_access_key = ""
  #   aws.keypair_name = "HAP"
  # 
  #   aws.ami = "ami-ad184ac4"
  # 
  #   override.ssh.username = "ubuntu"
  #   override.ssh.private_key_path = "HAP.pem"
  # end
  
  config.vm.synced_folder ".", "/vagrant", nfs: true
  
  config.vm.provision :shell, :path => "etc/provision.sh"
end
