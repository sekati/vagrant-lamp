Vagrant LAMP
============

A manicured devops Debian Squeeze 64bit LAMP stack configuration for Vagrant.

Installation:
-------------

1. Install [Vagrant](http://downloads.vagrantup.com/)

2. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

3. Add the `squeeze64` basebox:

	```$ vagrant box add squeeze64 http://cdn.sekati.com/vagrant/squeeze64.box```

4. Create (or go to an existing) project directory, initialize & launch the box:

	```
    	$ mkdir my-project
    	$ cd my-project/
    	$ vagrant init squeeze64
    	$ vagrant up
	```

5. Launch your project in-browser (being served by apache): [http://localhost:8080](http://localhost:8080).


What's Inside:
--------------

Installed Software:

* Apache (preconfigured)
* MySQL
* PHP (cli, curl, gd, geoip, imagick, mcrypt, memcached, mysql, sasl, sqlite, suhosin, xmlrpc, xsl)
* phpMyAdmin
* Ruby, Chef, Puppet
* git, git-deploy, subversion
* vim, screen, byobu, nano, curl, wget, links
* [MailCatcher](http://mailcatcher.me/) - all system/php mail routes here.
* [SSMTP](http://packages.debian.org/squeeze/ssmtp) on port 25 wrapping MailCatcher
* tailored bash dotfiles with many essentials ...


Services:

* phpMyAdmin: [http://localhost:8080/phpmyadmin](http://localhost:8080/phpmyadmin)
* PHPInfo: [http://localhost:8080/phpinfo](http://localhost:8080/phpinfo)
* MailCatcher [http://localhost:1080](http://localhost:1080)


Port Mapping:

The basebox's default Vagrantfile automatically forwards the following ports from guest to host:

```
  config.vm.forward_port 80, 8080     # HTTP
  config.vm.forward_port 443, 4430    # HTTPS
  config.vm.forward_port 3306, 3306   # MYSQL
  config.vm.forward_port 1025, 1025   # MailCatcher
  config.vm.forward_port 1080, 1080   # MailCatcher Frontend
  ```

Port Remap Firewall Script:

Users may wish to re-map the VM to standard HTTP(S) ports rather than 8080/4430. MacOS X users may
do so by downloading the `Firewall` folder from this repository & placing it in `/Library/StartupItems/`
& rebooting their machine - allowing them to access `http://localhost` & `https://localhost` for their
project.
