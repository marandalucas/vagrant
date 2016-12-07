
Vagrant.configure("2") do |config|
  config.vm.define :brfe01 do |brfe01|
    brfe01.vm.box = "debian/contrib-jessie64"
    brfe01.vm.hostname = "br-fe-01"
    brfe01.vm.network "private_network", ip: "192.168.221.101"
    brfe01.vm.network "public_network", bridge: "wlan0" ,ip: "192.168.0.101"
    brfe01.vm.provision "shell", inline: <<-SHELL

        echo  "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDNLW492ZSKmXJh2ugJDsts/mw/NVJdFiWD/sdRxVOlNQi0P1JN9ptg0BIfBrNBUjdRSEY8FPQM54XpnhxF8LBIlB1He5BAr3m5d0NIJv/2fTdwlYpuC+/se92BLdaISIwff9TvNyTRAIaL6zJ1yMK63MPF0jupNwebolwxHnr03ngfaD51eXLruXAwvSb8iBBbsgd37EgIZn1Byd3AQMl8cC21yx1Sf2gbesdrX0VJtEKmZaPksCMix0vbYOyF/dhoPG47NKFW9Y2POqj0f7FcUYc2ucll1B4i3VqhkhyA/DfguvxHoqZcWVRyjgdSu9YZlPwVf9eX0IW+Z7S/xoIh mc@debianmc" >> /home/vagrant/.ssh/authorized_keys

        sudo su

        ssh-keygen -t rsa -N "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDNLW492ZSKmXJh2ugJDsts/mw/NVJdFiWD/sdRxVOlNQi0P1JN9ptg0BIfBrNBUjdRSEY8FPQM54XpnhxF8LBIlB1He5BAr3m5d0NIJv/2fTdwlYpuC+/se92BLdaISIwff9TvNyTRAIaL6zJ1yMK63MPF0jupNwebolwxHnr03ngfaD51eXLruXAwvSb8iBBbsgd37EgIZn1Byd3AQMl8cC21yx1Sf2gbesdrX0VJtEKmZaPksCMix0vbYOyF/dhoPG47NKFW9Y2POqj0f7FcUYc2ucll1B4i3VqhkhyA/DfguvxHoqZcWVRyjgdSu9YZlPwVf9eX0IW+Z7S/xoIh mc@debianmc" -f ~/.ssh/id_rsa

        echo  "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDNLW492ZSKmXJh2ugJDsts/mw/NVJdFiWD/sdRxVOlNQi0P1JN9ptg0BIfBrNBUjdRSEY8FPQM54XpnhxF8LBIlB1He5BAr3m5d0NIJv/2fTdwlYpuC+/se92BLdaISIwff9TvNyTRAIaL6zJ1yMK63MPF0jupNwebolwxHnr03ngfaD51eXLruXAwvSb8iBBbsgd37EgIZn1Byd3AQMl8cC21yx1Sf2gbesdrX0VJtEKmZaPksCMix0vbYOyF/dhoPG47NKFW9Y2POqj0f7FcUYc2ucll1B4i3VqhkhyA/DfguvxHoqZcWVRyjgdSu9YZlPwVf9eX0IW+Z7S/xoIh mc@debianmc" >> /root/.ssh/authorized_keys

    SHELL
    brfe01.vm.provider "virtualbox" do |vbox|
      vbox.customize ["modifyvm", :id, "--memory", "2098"]
      vbox.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"] # eth2
      vbox.customize ["createhd",
                      '--filename', "tmp/disk.vdi",
                      '--size', "3000" ]
      vbox.customize ['storageattach', :id,
                     '--storagectl', 'SATA Controller',
                     '--port', 1,
                     '--device', 0,
                     '--type', 'hdd',

                     '--medium', "tmp/disk.vdi"]
    end
  end
    config.vm.define :chfe01 do |chfe01|
      chfe01.vm.box = "debian/contrib-jessie64"
      chfe01.vm.hostname = "ch-fe-01"
      chfe01.vm.network "private_network", ip: "192.168.221.102"
      chfe01.vm.provision "shell", inline: <<-SHELL

        echo  "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDNLW492ZSKmXJh2ugJDsts/mw/NVJdFiWD/sdRxVOlNQi0P1JN9ptg0BIfBrNBUjdRSEY8FPQM54XpnhxF8LBIlB1He5BAr3m5d0NIJv/2fTdwlYpuC+/se92BLdaISIwff9TvNyTRAIaL6zJ1yMK63MPF0jupNwebolwxHnr03ngfaD51eXLruXAwvSb8iBBbsgd37EgIZn1Byd3AQMl8cC21yx1Sf2gbesdrX0VJtEKmZaPksCMix0vbYOyF/dhoPG47NKFW9Y2POqj0f7FcUYc2ucll1B4i3VqhkhyA/DfguvxHoqZcWVRyjgdSu9YZlPwVf9eX0IW+Z7S/xoIh mc@debianmc" >> /home/vagrant/.ssh/authorized_keys

        sudo su

        ssh-keygen -t rsa -N "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDNLW492ZSKmXJh2ugJDsts/mw/NVJdFiWD/sdRxVOlNQi0P1JN9ptg0BIfBrNBUjdRSEY8FPQM54XpnhxF8LBIlB1He5BAr3m5d0NIJv/2fTdwlYpuC+/se92BLdaISIwff9TvNyTRAIaL6zJ1yMK63MPF0jupNwebolwxHnr03ngfaD51eXLruXAwvSb8iBBbsgd37EgIZn1Byd3AQMl8cC21yx1Sf2gbesdrX0VJtEKmZaPksCMix0vbYOyF/dhoPG47NKFW9Y2POqj0f7FcUYc2ucll1B4i3VqhkhyA/DfguvxHoqZcWVRyjgdSu9YZlPwVf9eX0IW+Z7S/xoIh mc@debianmc" -f ~/.ssh/id_rsa

        echo  "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDNLW492ZSKmXJh2ugJDsts/mw/NVJdFiWD/sdRxVOlNQi0P1JN9ptg0BIfBrNBUjdRSEY8FPQM54XpnhxF8LBIlB1He5BAr3m5d0NIJv/2fTdwlYpuC+/se92BLdaISIwff9TvNyTRAIaL6zJ1yMK63MPF0jupNwebolwxHnr03ngfaD51eXLruXAwvSb8iBBbsgd37EgIZn1Byd3AQMl8cC21yx1Sf2gbesdrX0VJtEKmZaPksCMix0vbYOyF/dhoPG47NKFW9Y2POqj0f7FcUYc2ucll1B4i3VqhkhyA/DfguvxHoqZcWVRyjgdSu9YZlPwVf9eX0IW+Z7S/xoIh mc@debianmc" >> /root/.ssh/authorized_keys

    SHELL
      chfe01.vm.provider "virtualbox" do |vbox|
      vbox.customize ["modifyvm", :id, "--memory", "2048"]
    end
  end
end
