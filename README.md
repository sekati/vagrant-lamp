Vagrant LAMP
============

A manicured devops Debian Squeeze 64bit LAMP stack configuration for Vagrant.

Installation:
-------------

1. Install [Vagrant](http://downloads.vagrantup.com/)

2. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

3. Add the `squeeze64` basebox:

```
    $ vagrant box add squeeze64 http://cdn.sekati.com/vagrant/squeeze64.box
```

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
* zsh with [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
* git, git-deploy, subversion
* vim, screen, byobu, nano, curl, wget, links
* [MailCatcher](http://mailcatcher.me/) - all system/php mail routes here.
* [SSMTP](http://packages.debian.org/squeeze/ssmtp) on port 25 wrapping MailCatcher
* tailored bash dotfiles with many essentials ...


Services:

* phpMyAdmin: [http://localhost:8080/phpmyadmin](http://localhost:8080/phpmyadmin)
* phpinfo: [http://localhost:8080/phpinfo](http://localhost:8080/phpinfo)
* Mailcatcher [http://localhost:1080](http://localhost:1080)
