Vagrant.configure("2") do |config|

  config.vm.box      = 'precise32'
  config.vm.box_url  = 'http://files.vagrantup.com/precise32.box'

  config.vm.synced_folder "~/projects/", "/home/vagrant/projects/"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end

  config.vm.provider 'parallels' do |v, override|
    override.vm.box = 'parallels/ubuntu-12.04'
    override.vm.box_url = 'https://vagrantcloud.com/parallels/ubuntu-12.04'

    # Can be running at background, see https://github.com/Parallels/vagrant-parallels/issues/39
    v.customize ['set', :id, '--on-window-close', 'keep-running']
  end

  config.vm.provision :chef_solo do |chef|
    chef.json = {
      "elixir" => {
        "elixir_git_ref" => "v0.12.4"
      }
    }
    chef.add_recipe "apt::default"
    chef.add_recipe "erlang"
    chef.add_recipe "elixir"
  end
end
