
$script = <<-'SCRIPT'
yes | sudo ufw enable
sudo ufw allow 22
sudo apt update && sudo apt upgrade -y
curl -fsSL https://get.docker.com -o get-docker.sh
sudo bash /home/vagrant/get-docker.sh
sudo usermod -aG docker vagrant
sudo apt-get install docker-compose-plugin -y
sudo apt autoremove -y

SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.provision "shell", inline: $script

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 1
  end
end
