Vagrant.configure("2") do |config|
  config.vm.define "web3" do |web3|
    web3.vm.box = "ubuntu/bionic64"
    web3.vm.hostname = "web3"
    web3.vm.network "private_network", type: "dhcp"
    web3.vm.synced_folder ".", "/vagrant"

    web3.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "/vagrant/provision/playbook.yml"
      ansible.inventory_path = "/vagrant/provision/inventario"
      ansible.limit = "webservers"
    end
  end
end