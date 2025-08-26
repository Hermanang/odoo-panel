Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  # Définir la machine virtuelle "ubuntu"
  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.network "forwarded_port", guest: 8069, host: 8069, host_ip: "127.0.0.1"
    ubuntu.vm.hostname = "ubuntu"
  end

  # Deuxième VM : Ubuntu Jammy (22.04)
  config.vm.define "jammy" do |jammy|
    jammy.vm.box = "ubuntu/jammy64"
    jammy.vm.network "private_network", ip: "192.168.56.12"  # <-- IP joignable
    jammy.vm.network "forwarded_port", guest: 8070, host: 8070, host_ip: "127.0.0.1"
    jammy.vm.hostname = "jammy"
  end
  
end
