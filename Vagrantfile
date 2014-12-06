Vagrant.configure("2") do |config|

  config.vm.box = "CentOS_6_4_64"

  config.vm.network :private_network, ip: "192.168.33.40"
  config.ssh.forward_agent = true

  #############################################################
  # Ansible provisioning (you need to have ansible installed)
  #############################################################


  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.inventory_path = "ansible/inventories/dev"
    ansible.limit = 'all'
  end

  config.vm.synced_folder "./", "/vagrant", type: "nfs"
end