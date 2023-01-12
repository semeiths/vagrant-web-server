Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"
  config.vm.box_version = "11.20221219.1"
  config.vm.synced_folder "webcontent", "/var/www/html", type: "nfs", nfs_version: 4
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.provision "shell", inline: <<-SHELL
    echo "Provisioning machine..."
    apt update
    apt install python -y python3 python3-pip neovim apache2
    echo "Machine successfully provisioned at $(date)!"
  SHELL
end