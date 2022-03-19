Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "node-1"
  #config.vm.network "forwarded_port", guest: 3000, host: 8081
  config.vm.network "public_network", bridge: "eno1"
   config.vm.provision "shell", inline: <<-SHELL
     apt-get update
     apt-get install -y docker.io
     #manager
     docker swarm join --token SWMTKN-1-3go8nivt9p4t0f20zatzbkjbdlb2laqbvsj4rylqimkyimxszj-c9i3yhkv1qgvorij3aqzemf33 192.168.1.3:2377
     #worker
     #docker swarm join --token SWMTKN-1-3go8nivt9p4t0f20zatzbkjbdlb2laqbvsj4rylqimkyimxszj-3w50bo8bhwyhayk47yh0c42g8 192.168.1.3:2377
   SHELL
end
