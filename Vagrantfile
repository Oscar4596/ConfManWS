
Vagrant.configure("2") do |config|

  config.vm.define "master" do |master|
    master.vm.box = "hashicorp/bionic64"
    master.vm.network "public_network", ip: "192.168.0.17"
    master.vm.provision "file", source: "ansible/hosts", destination: "~/hosts"
    master.vm.provision "shell", path: "ansible/ansiblehost.sh"
  end
 
  config.vm.define "puppet" do |puppet|
    puppet.vm.box = "hashicorp/bionic64"
    puppet.vm.network "public_network", ip: "192.168.0.18"
    puppet.vm.network "forwarded_port", guest: 80, host: 8081
  end

end
