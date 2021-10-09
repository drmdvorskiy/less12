Vagrant.configure("2") do |config|

  config.vm.provision "file", source: "key/id_rsa.pub", destination: "/home/vagrant/.ssh/id_rsa.pub"
  config.vm.provision "shell", inline: <<-SHELL
    cat /home/vagrant/.ssh/id_rsa.pub >> /home/vagrant/.ssh/authorized_keys
  SHELL

  config.vm.define "nginx" do |nginx|
    nginx.vm.box = "ubuntu/focal64"
    nginx.vm.hostname = "nginx"
    nginx.vm.network "private_network", ip: "192.168.6.2", hostname: true
    nginx.vm.synced_folder ".", "/vagrant", disabled: true
    nginx.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
    end
  end

  config.vm.define "consul1" do |consul1|
    consul1.vm.box = "ubuntu/focal64"
    consul1.vm.hostname = "consul1"
    consul1.vm.network "private_network", ip: "192.168.6.3", hostname: true
    consul1.vm.synced_folder ".", "/vagrant", disabled: true
    consul1.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
    end
  end

  config.vm.define "consul2" do |consul2|
    consul2.vm.box = "ubuntu/focal64"
    consul2.vm.hostname = "consul2"
    consul2.vm.network "private_network", ip: "192.168.6.5", hostname: true
    consul2.vm.synced_folder ".", "/vagrant", disabled: true
    consul2.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
    end
  end

  config.vm.define "consul3" do |consul3|
    consul3.vm.box = "ubuntu/focal64"
    consul3.vm.hostname = "consul3"
    consul3.vm.network "private_network", ip: "192.168.6.4", hostname: true
    consul3.vm.synced_folder ".", "/vagrant", disabled: true
    consul3.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
    end
  end

end
