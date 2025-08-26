Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  # Définir la machine virtuelle "ubuntu"
  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.network "private_network", ip: "192.168.56.11"  # <-- IP joignable
    ubuntu.vm.hostname = "ubuntu"
  end

  # Deuxième VM : Ubuntu Jammy (22.04)
  config.vm.define "jammy" do |jammy|
    jammy.vm.box = "ubuntu/jammy64"
    jammy.vm.network "private_network", ip: "192.168.56.12"  # <-- IP joignable
    jammy.vm.hostname = "jammy"
  end
  
end
