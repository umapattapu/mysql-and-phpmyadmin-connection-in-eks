# mysql-and-phpmyadmin-connection-in-eks
# login php pod 
# kubect exec -it pod-name -- /bin/bash
# sudo nano /etc/phpmyadmin/config.inc.php
  check that files in php container
# $cfg['Servers'][$i]['controluser'] = 'pma'; 
# $cfg['Servers'][$i]['controlpass'] = 'pmapass';
  Next login in mysql container
# kubectl exec -it sql-name -- /bin/bash
# mysql -u root -p 1234
# CREATE USER 'pma'@'%' IDENTIFIED BY 'pmapass';
# GRANT ALL PRIVILEGES ON *.* TO 'pma'@'%' WITH GRANT OPTION;
#use multitenency;
#GRANT ALL PRIVILEGES ON multitenancy.* TO 'myuser'@'%' WITH GRANT OPTION;  
#FLUSH PRIVILEGES;  
# https://stackoverflow.com/questions/46736319/phpmyadmin-error-mysqli-real-connect-hy000-1045-access-denied-for-user-p
