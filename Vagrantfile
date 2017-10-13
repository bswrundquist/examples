
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end
  config.disksize.size = '75GB'
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "public_network", ip: "192.168.1.17" 
  config.vm.network "forwarded_port", guest: 8080, host: 8080, host_ip: "localhost"
  config.vm.network "forwarded_port", guest: 9090, host: 9090, host_ip: "localhost"
  config.vm.network "forwarded_port", guest: 9000, host: 9000, host_ip: "localhost"
  config.vm.network "forwarded_port", guest: 8787, host: 8787, host_ip: "localhost"
  config.vm.network "forwarded_port", guest: 8788, host: 8788, host_ip: "localhost"
  config.vm.network "forwarded_port", guest: 8789, host: 8789, host_ip: "localhost"
  config.vm.network "forwarded_port", guest: 5480, host: 5480, host_ip: "localhost"
  config.vm.network "forwarded_port", guest: 8888, host: 8888, host_ip: "localhost"
  config.vm.synced_folder "../data", "/data" # JSON files for Mongodb
  config.vm.synced_folder ".", "/home/vagrant"
  config.vm.provider "virtualbox" do |vb|
    vb.memory =  6000 
    vb.cpus = 2
  end
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
  SHELL
  config.vm.provision :docker
  #config.vm.provision :docker_compose
end

