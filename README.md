# Ansible Playbooks


## Roles

* Common
	* python-apt
	* python-software-properties
	* ack-grep
	* vim
	* git
	* ntp
	* [willian/vimfiles](http://github.com/willian/vimfiles)
	* [willian/vagrant-config](http://github.com/willian/vagrant-config)
* Memcached
* nginx
* NodeJS
* PostgreSQL
* Redis
* Ruby 2.0
	* Bundler

## Vagrantfile
```ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "BoxName"
  # config.vm.synced_folder ".", "/vagrant", nfs: true

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "/full/path/to/ansible-playbooks/playbook.yml"
    ansible.extra_vars = { nginx_hosts: ["YOUR_APPLICATION_HOSTNAME"] }
  end
end
```

**Don't forget to replace `YOUR_APPLICATION_HOSTNAME` above.**

## Contributing
1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
