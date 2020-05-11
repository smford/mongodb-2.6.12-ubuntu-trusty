# mongodb-2.6.12-ubuntu-trusty

There is no easily available package to install MongoDB 2.6.12 for Ubuntu Trusty, these instructions show you how to do it.

## Requirements
- rbenv

```
git clone git@github.com:smford/mongodb-2.6.12-ubuntu-trusty.git
cd mongodb-2.6.12-ubuntu-trusty

rbenv install 2.6.5
rbenv local 2.6.5
gem install --no-document fpm

wget http://downloads.mongodb.org/linux/mongodb-linux-x86_64-2.6.12.tgz
tar xzvf mongodb-linux-x86_64-2.6.12.tgz

fpm -s dir -t deb -n mongo --after-install deb-scripts/postinst --before-remove deb-scripts/prerm --after-remove deb-scripts/postrm -v 2.6.12 files/mongodb.conf-daemon=/etc/mongodb.conf files/mongodb.conf-init=/etc/init/mongodb.conf mongodb-linux-x86_64-2.6.12/bin/=/usr/bin/
```

You can now install mongo by
`dpkg -i mongo_2.6.12_amd64.deb`
