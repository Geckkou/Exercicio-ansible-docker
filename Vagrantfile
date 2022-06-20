Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"

    config.vm.provider "virtualbox" do |vb|
        vb.memory = 1024
    end

    #Criando e configurando a Vm com um ip estático 
    #Aqui támbem é feito o acessso a pasta compartilhada do host com a VM
    #uma chave ssh é transferida para dentro da Vm para ser feita a conexão 
    config.vm.define "docker" do |doc|
        doc.vm.network "private_network", ip: "192.168.50.4"
        doc.vm.provision "shell", inline: "cat /vagrant/config/ssh_conector.pub >> .ssh/authorized_keys"
    end
end

    