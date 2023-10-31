Vagrant.configure("2") do |config|

  config.vm.define "web" do |web|
    web.vm.box = "generic/alpine38"
    config.vm.network "public_network"
    puppet.vm.hostname = "web"

    config.vm.synced_folder "./data", "/vagrant_data"
  
    config.vm.provider "virtualbox" do |vb|
      vb.gui = true
    
      vb.memory = "1024"
      vb.name = "alpine-test1"
    end

    config.vm.provision "shell", path: "script.sh"
  end

  config.vm.define "db" do |db|
    db.vm.box = "generic/alpine38"
    config.vm.network "public_network"
  
    config.vm.provider "virtualbox" do |vb|
      vb.gui = true
    
      vb.memory = "1024"
      vb.name = "alpine-test2"
    end
   
    config.vm.provision "shell", path: "script.sh"
  end

end
