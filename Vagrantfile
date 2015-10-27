# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "scotch/box" # This is a modified Ubuntu iso with node, grunt, bower
    config.vm.network "private_network", ip: "192.168.33.10" # ip address for accessing the shared files
    config.vm.hostname = "enlite"
    config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }
    config.ssh.username = "vagrant"
	config.ssh.password = "vagrant"
    config.vm.provision "shell", inline: <<-SHELL

        ## Only thing you probably really care about is right here
        ## here you can create virtual domians like this DOMAINS=("enlite.local enlite2.local") 
        DOMAINS=("enlite.local") 

        ## Loop through all sites
        for ((i=0; i < ${#DOMAINS[@]}; i++)); do

            ## Current Domain
            DOMAIN=${DOMAINS[$i]}

            echo "Creating directory for $DOMAIN..."
            mkdir -p /var/www/$DOMAIN/public

            echo "Creating vhost config for $DOMAIN..."
            sudo cp /etc/apache2/sites-available/scotchbox.local.conf /etc/apache2/sites-available/$DOMAIN.conf

            echo "Updating vhost config for $DOMAIN..."
            sudo sed -i s,scotchbox.local,$DOMAIN,g /etc/apache2/sites-available/$DOMAIN.conf
            sudo sed -i s,/var/www/public,/var/www/$DOMAIN/public,g /etc/apache2/sites-available/$DOMAIN.conf

            echo "Enabling $DOMAIN. Will probably tell you to restart Apache..."
            sudo a2ensite $DOMAIN.conf

            echo "So let's restart apache..."
            sudo service apache2 restart
            ## dump.sql just drop the file in the root folder and change this "yourdatabase" to your DB's name
            ## mysql -u root -proot yourdatabase < /var/www/dump.sql

        done

    SHELL

end

