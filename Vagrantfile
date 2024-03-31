Vagrant.configure("2") do |config|
#  config.vm.provider "virtualbox" do |vb|
#    vb.name = "mv01"
#    vb.memory = 2048
#    vb.cpus = 2
#  end

  config.vm.box = "hashicorp/bionic64"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "public_network", ip: "192.168.0.50"
  config.vm.provision "shell", path: "script.sh"
  config.vm.synced_folder "site/", "/var/www/html"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
