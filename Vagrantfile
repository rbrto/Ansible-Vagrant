Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "192.168.33.21"
  # sincroniza todo el proyecto local dentro del var/www en el server
  config.vm.synced_folder ".", "/var/www"

  # al hacer vagrant up automaticamente me lama al playbook.yml usando el provision de ansible
  config.vm.provision :ansible do |ansible|
    ansible.limit = "local" #limit vagrant to local group
    ansible.inventory_path = "hosts"
    ansible.playbook = "site.yml"
  end

end
