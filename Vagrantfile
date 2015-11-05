Vagrant.configure(2) do |config|
  config.ssh.private_key_path = "./ssh-keys/rackspace_rsa"
  config.vm.provider :rackspace do |rs|
    rs.username = ENV['RACKSPACE_USERNAME']
    rs.api_key  = ENV['RACKSPACE_API_KEY']
    rs.admin_password = ENV['ANSIBLE_CONTROLLER_ROOT_PASSWORD']
    rs.flavor   = /1 GB Performance/
    rs.image    = /Ubuntu 12.04/
    rs.rackspace_region = :dfw
    rs.server_name =  "ansible-controller"
    rs.public_key_path  = "./ssh-keys/rackspace_rsa.pub"
  end
  config.vm.provision :shell, :inline => $script
  # config.vm.provision "ansible" do |ansible|
  #   ansible.playbook = "./ansible/rtbkit-play.yml"
  # end
end
