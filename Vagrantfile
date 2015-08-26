Vagrant.configure("2") do |config|
	config.vm.box = "hashicorp/precise64"
	config.vm.network :private_network, ip: "192.168.56.11"

	config.ssh.forward_agent = true

	config.vm.provider "virtualbox" do |v|
	    v.name = "libs-vm"
	    v.customize ["modifyvm", :id, "--memory", "768"]
	end

	config.vm.provision "file", source: "~/.gitconfig", destination: "~/.gitconfig"
	config.vm.provision "shell", path: "provision/bootstrap.sh"
end
