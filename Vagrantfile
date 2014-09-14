# Vagrantfile
#
# Configuration of the vagrant machine.

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.hostname = "trusty64"
  # static ip on bridged network
  config.vm.network :public_network, ip: "192.168.1.120"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible/system.yml"
    ansible.sudo = true

    ansible.extra_vars = {
      # git repository for zsh dotfiles
      #zsh_git_url: "https://github.com/enil/enil-zsh-dotfiles.git",

      # git repository for vim dotfiles
      #vim_git_url: "https://github.com/enil/enil-vim-dotfiles.git",

      # additional packages to install
      extra_packages: %w[tmux vim build-essential],

      # don't check repos for updates
      update_repos: false
    }
  end
end

# -*- mode: ruby -*-
# vi: set ft=ruby :
