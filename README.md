Vagrant LAMP
============

A manicured devops Debian Squeeze 64bit LAMP stack configuration for Vagrant.

Installation:
-------------

Install [vagrant](http://downloads.vagrantup.com/)

    $ gem install vagrant

Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

Add this basebox (name of the box is supposed to be squeeze64)

    $ vagrant box add squeeze64 http://cdn.sekati.com/vagrant/squeeze64.box

Clone this repository

Go to the repository folder and launch the box

    $ cd [repo]
    $ vagrant up

What's inside:
--------------

Installed software:

* Apache (preconfigured)
* MySQL
* PHP (cli, curl, gd, geoip, imagick, mcrypt, memcached, mysql, sasl, sqlite, suhosin, xmlrpc, xsl)
* phpMyAdmin
* zsh with [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
* git, git-deploy, subversion
* vim, screen, byobu, nano, curl, wget, links
* [MailCatcher](http://mailcatcher.me/)
* [SSMTP](http://packages.debian.org/squeeze/ssmtp) on port 25 wrapping MailCatcher
* tailored bash dotfiles with many essentials ...

Apache virtual hosts are created in `public` folder or optionally in a per site configurable docroot and configured with data bag `sites`.
Apache serves the projects docroot (e.g. this cloned directory containing the `Vagrantfile`) via http & https.

phpMyAdmin & phpinfo are available @:

* http://localhost:8080/phpmyadmin -or- http://localhost:8080/pma
* http://localhost:8080/phpinfo

PHP & system routes mail to MailCatcher. The web frontend for MailCatcher is running @:

* http://localhost:1080
