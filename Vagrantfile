Vagrant.configure("2") do |config|
  servers=[
    {
      :hostname => "control",
      :box => "ubuntu/bionic64",
      :ip => "172.16.1.50",
      :ssh_port => '2200'  
    },
    {
      :hostname => "node1",
      :box => "ubuntu/bionic64",
      :ip => "172.16.1.51",
      :ssh_port => '2201'
    },
    {
      :hostname => "node2",
      :box => "ubuntu/bionic64",
      :ip => "172.16.1.52",
      :ssh_port => '2202'
    },
    {
      :hostname => "node3",
      :box => "ubuntu/bionic64",
      :ip => "172.16.1.53",
      :ssh_port => '2203'
    }
  ]

  config.vm.define "control" do |control|
    control.vm.box = servers[0][:box]
    control.vm.hostname = servers[0][:hostname] 
    control.ssh.insert_key = false
    control.vm.network "private_network", ip: servers[0][:ip]
    control.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end

    control.vm.network "forwarded_port", guest: 22, host: servers[0][:ssh_port], id: "ssh"
    control.ssh.port = servers[0][:ssh_port]

    control.vm.provision "shell", inline: <<-SHELL

      #copying vital files to the control server
      sudo cp /vagrant/hosts /etc/
      sudo cp -r /vagrant/solution /home/vagrant/
      sudo cp /vagrant/config /home/vagrant/.ssh/config
      sudo cp /vagrant/vagrant.key.rsa /home/vagrant/.ssh/vagrant.key.rsa

      #Generating ssh keypair with ownership and permissions for the control to replace vagrant generated insecure key.
      ssh-keygen -t ed25519 -f /home/vagrant/.ssh/control_id_ed25519 -C 'control default'
      sudo chown vagrant:vagrant /home/vagrant/.ssh/control_id_ed25519*
      sudo chmod 600 /home/vagrant/.ssh/control_id_ed25519.pub
      eval $(ssh-agent -s)
      ssh-add /home/vagrant/.ssh/control_id_ed25519
      
      #Permissions and ownerships of copied 
      sudo chown -R vagrant:vagrant /home/vagrant/solution
      sudo chmod -R 755 /home/vagrant/solution
      sudo chown vagrant:vagrant /home/vagrant/.ssh/config
      
      # Install Ansible and its dependencies
      sudo apt-get update
      sudo apt-get install -y software-properties-common
      sudo apt-add-repository -y --update ppa:ansible/ansible
      sudo apt-get install -y ansible
    SHELL
  end

  servers[1..].each do |machine|
    config.vm.define machine[:hostname] do |node|
      node.vm.box = machine[:box]
      node.ssh.insert_key = false
      node.vm.hostname = machine[:hostname]
      node.vm.network :private_network, ip: machine[:ip]
      node.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", 512]
        vb.customize ["modifyvm", :id, "--cpus", 1]
      end

      node.vm.provision "shell", inline: <<-SHELL
        sudo sed -i "s/#Port 22/Port #{machine[:ssh_port]}/g" /etc/ssh/sshd_config
        sudo systemctl restart sshd
        sudo cp /vagrant/hosts /etc/hosts
      SHELL
    end
  end
end





    

 
