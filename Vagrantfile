Vagrant.configure("2") do |config|
  # Конфигурация виртуальной машины Windows 10
  config.vm.define "windows" do |windows|
    windows.vm.box = "your_windows_box"
    windows.vm.network "private_network", ip: "192.168.1.2"
    windows.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "2048"
    end
  end

  # Конфигурация виртуальной машины Debian
  config.vm.define "debian" do |debian|
    debian.vm.box = "your_debian_box"
    debian.vm.network "private_network", ip: "192.168.1.3"
    debian.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "1024"
    end

    # Настройка маршрутизации через Windows 10
    debian.vm.provision "shell", inline: <<-SHELL
      ip route add default via 192.168.1.2
    SHELL
  end
end
