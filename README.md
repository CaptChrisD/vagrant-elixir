# vagrant-elixir
A Vagrant environment (precise32) with required chef recipes for Elixir

## Requirements

* [VirtualBox](https://www.virtualbox.org) or [Parallels Desktop](http://www.parallels.com/products/desktop/)(need Vagrant 1.5+, see [vagrant-parallels](http://parallels.github.io/vagrant-parallels/docs/installation/index.html))

* [Vagrant 1.1+](http://vagrantup.com) (not a Ruby gem)

* Create folder '~/projects' to share with the VM or set SHARED_DIR variable when running vagrant up ( host $ SHARED_DIR=~/code vagrant up )

## How To Build The Virtual Machine

Building the virtual machine is this easy:

    host $ git clone https://github.com/CaptChrisD/vagrant-elixir.git
    host $ cd vagrant-elixir
		host $ Run 'git submodule init'
		host $ Run 'git submodule update'
    host $ vagrant up

That's it.

(If you want to use Parallels Desktop instead of VirtualBox, you need Vagrant 1.5+, and write `vagrant up --provider=parallels` instead of `vagrant up` when building the VM for the first time. After that, Vagrant will remember your provider choice, and you won't need to include the `provider` flag again.)

If the base box is not present that command fetches it first. The setup itself takes about 3 minutes in my MacBook Air. After the installation has finished, you can access the virtual machine with

    host $ vagrant ssh
    Welcome to Ubuntu 12.04 LTS (GNU/Linux 3.2.0-23-generic-pae i686)
    ...
    vagrant@rails-dev-box:~$
