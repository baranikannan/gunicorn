Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provider "virtualbox" do |vb|
     vb.memory = 2048
     vb.cpus = 4  
  config.vm.network "private_network", ip: "10.10.10.20"
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "files/playbook.yml"
    ansible.become  = "yes"
    ansible.become_user = "root"
  end
end
