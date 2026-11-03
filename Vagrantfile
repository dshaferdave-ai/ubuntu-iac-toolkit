Vagrant.configure("2") do |config|
  # Tell Vagrant to fetch a fresh, official Ubuntu 22.04 box
  config.vm.box = "ubuntu/jammy64"

  # Give it a private IP so we can talk to it later
  config.vm.network "private_network", ip: "192.168.56.10"

  # FIX: Tell Vagrant NOT to create a shared folder across the WSL border
  config.vm.synced_folder ".", "/vagrant", disabled: true
end
