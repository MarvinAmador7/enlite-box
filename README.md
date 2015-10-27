Enlite Cloud Vagrant Box
==========

## What and Why

Vagrant is an extremely powerful tool. With Chef or Puppet and Vagrant, you can configure any type of server environment you can think of. The possibilities are endless (especially with Docker in the picture now, too).

> If your new to Vagrant, this link [Vagrant web site][1]


## Features

### System Stuff

- Ubuntu 14.04 LTS (Trusty Tahr)
- PHP 5.6
- Ruby 2.2.x
- Vim
- Git
- cURL
- GD and Imagick
- Composer
- Beanstalkd
- Node
- NPM
- Mcrypt

### Database Stuff
- MySQL
- PostgreSQL
- SQLite

### Caching Stuff

- Redis
- Memcache and Memcached

### Node Stuff

- Grunt
- Bower
- Yeoman
- Gulp
- Browsersync ## awesome live reload and device sync :)
- PM2

### Laravel Stuff

- Laravel Installer
- Laravel Envoy
- Blackfire Profiler

### Other Useful Stuff

- No Internet connection required
- PHP Errors turned on
- Laravel and WordPress ready
- Operating System agnostic
- Goodbye XAMPP / WAMP
- Super easy database access and control
- Virtual host ready virtual-hosts
- PHP short tags turned on
- H5BP’s server configs

## Get Started

* Download and Install [Vagrant][1]
* Download and Install [VirtualBox][2]
* Clone the modified Ubuntu Box [GitHub Repository](https://github.com/MarvinAmador7/enlite-box.git)
* Run ``` vagrant up ```
* Access Your Project at  [http://192.168.33.10/][7]

## Basic Vagrant Commands


### Start or resume your server
```bash
vagrant up
```

### Pause your server
```bash
vagrant suspend
```

### Delete your server
```bash
vagrant destroy
```

### SSH into your server
```bash
vagrant ssh
```



## Database Access

### MySQL 

- Hostname: localhost or 127.0.0.1
- Username: root
- Password: root
- Database: scotchbox // you can create many DBs, this is a default for the modified Box

### PostgreSQL

- Hostname: localhost or 127.0.0.1
- Username: root
- Password: root
- Database: scotchbox
- Port: 5432

## SSH Access

- Hostname: 127.0.0.1:2222
- Username: vagrant
- Password: vagrant


## Updating the Box

Although not necessary, if you want to check for updates, just type:

```bash
vagrant box outdated
```

It will tell you if you are running the latest version or not, of the box. If it says you aren't, simply run:

```bash
vagrant box update
```


## Setting a Hostname

If you prefer to develop at a domain name versus an IP address. If you want to get rid of the some-what ugly IP address, just add a record like the following example to your computer's host file.

```bash
192.168.33.10 whatever-i-want.local
```

Or if you want "www" to work as well, do:

```bash
192.168.33.10 whatever-i-want.local www.whatever-i-want.local
```

Technically you could also use a Vagrant Plugin like [Vagrant Hostmanager][4] to automatically update your host file when you run Vagrant Up. However, the purpose of this Box is to have as little dependencies as possible so that it's always working when you run "vagrant up".

 [1]: https://www.vagrantup.com/downloads.html
 [2]: https://www.virtualbox.org/wiki/Downloads
 [3]: http://www.sequelpro.com/
 [4]: https://github.com/smdahlen/vagrant-hostmanager
 [5]: https://www.virtualbox.org/wiki/Downloads
 [6]: https://github.com/smdahlen/vagrant-hostmanager
 [7]: http://192.168.33.10/
