# mongodb-2.6.12-ubuntu-trusty

```
git clone git@github.com:smford/mongodb-2.6.12-ubuntu-trusty.git
cd mongodb-2.6.12-ubuntu-trusty

rbenv install 2.6.5
rbenv local 2.6.5
gem install --no-document fpm

wget http://downloads.mongodb.org/linux/mongodb-linux-x86_64-2.6.12.tgz
tar xzvf mongodb-linux-x86_64-2.6.12.tgz

fpm -s dir -t deb -n mongo-test7 --after-install deb-scripts/postinst --before-remove deb-scripts/prerm --after-remove deb-scripts/postrm -v 2.6.12-govuk files/mongodb.conf=/etc/mongodb.conf mongodb-linux-x86_64-2.6.12/bin/=/usr/bin/


```
