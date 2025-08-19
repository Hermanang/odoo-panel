Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  # Définir la machine virtuelle "ubuntu"
  config.vm.define "ubuntu" do |ubuntu|
    # ubuntu.vm.network "forwarded_port", guest: 8069, host: 8069, host_ip: "127.0.0.1"
    ubuntu.vm.hostname = "ubuntu"
  end
end
