Installation

    Copy centreon-weathermap directory into centreon's modules location /usr/share/centreon/www/modules/ and set apache as its owner for all subfolders
    Grant write permission to apache at /usr/share/centreon/www/modules/centreon-weathermap/src/configs
    Grant write permission to centreon-engine at /usr/share/centreon/www/modules/centreon-weathermap/src/output
    A full permission to /usr/share/centreon/www/modules/centreon-weathermap/poller.php is advised
    Enable module on Centreon's extension manager

    The module installation script will try to find the localhost (127.0.0.1) in order to insert the weathermap poller service. Export the configuration files to activate this service.

Getting Started

Configuration > Weathermap

You may create, edit, delete, duplicate, enable/disable maps and groups by centreon's object manager

Reporting > Maps > Views

----

getfacl /usr/share/centreon/www/modules/centreon-weathermap/poller.php
setfacl -R -m u:centreon-engine:rwx /usr/share/centreon/www/modules/centreon-weathermap/src/output/
setfacl -R -m d:u:centreon-engine:rwx /usr/share/centreon/www/modules/centreon-weathermap/src/output/
getfacl /usr/share/centreon/www/modules/centreon-weathermap/src/output/
setfacl -R -m d:g:centreon-engine:wx /usr/share/centreon/www/modules/centreon-weathermap/src/output/
chown -R apache:apache  /usr/share/centreon/www/modules/centreon-weathermap/
chmod 777  /usr/share/centreon/config/centreon.config.php
chmod 777 /etc/centreon/centreon.conf.php
