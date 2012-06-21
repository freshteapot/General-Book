#Install solr extenstion for php 5.3

##Try
<pre>
pecl install -n solr
<pre>

If it fails, like it did for me.

##Install required packages.
<pre>
apt-get install libxml2-dev
apt-get install libcurl4-gnutls-dev
pecl install -n solr
<pre>

##Add solr to your php.ini
```
vim /etc/php5/conf.d/solr.ini
```

Add full path.
```
extension=/usr/lib/php5/20090626/solr.so
```

#Confirm all is well.
* Restart apache

* Via command line
```
php -i | grep 'solr'
```

* Via apache
Goto page with phpinfo

Search for solr.


Now go play with solr.

##Curious thing to note.
<pre>
solr

Solr Extension Version => 1.0.1
Solr Extension Revision Id => $Revision: 311799 $
</>

Even tho:
http://pecl.php.net/package/solr

##Look at the package and explore for yourself.


###Output from my install
It is worth looking int the directory downloaded from pear / pecl.

Build complete.
Don't forget to run 'make test'.

running: make INSTALL_ROOT="/tmp/pear/temp/pear-build-rootVRarSg/install-solr-1.0.2" install
Installing shared extensions:     /tmp/pear/temp/pear-build-rootVRarSg/install-solr-1.0.2/usr/lib/php5/20090626/
running: find "/tmp/pear/temp/pear-build-rootVRarSg/install-solr-1.0.2" | xargs ls -dils
703223   4 drwxr-xr-x 3 root root   4096 Jun 21 10:07 /tmp/pear/temp/pear-build-rootVRarSg/install-solr-1.0.2
703227   4 drwxr-xr-x 3 root root   4096 Jun 21 10:07 /tmp/pear/temp/pear-build-rootVRarSg/install-solr-1.0.2/usr
703228   4 drwxr-xr-x 3 root root   4096 Jun 21 10:07 /tmp/pear/temp/pear-build-rootVRarSg/install-solr-1.0.2/usr/lib
703229   4 drwxr-xr-x 3 root root   4096 Jun 21 10:07 /tmp/pear/temp/pear-build-rootVRarSg/install-solr-1.0.2/usr/lib/php5
703230   4 drwxr-xr-x 2 root root   4096 Jun 21 10:07 /tmp/pear/temp/pear-build-rootVRarSg/install-solr-1.0.2/usr/lib/php5/20090626
701612 848 -rwxr-xr-x 1 root root 864925 Jun 21 10:07 /tmp/pear/temp/pear-build-rootVRarSg/install-solr-1.0.2/usr/lib/php5/20090626/solr.so

Build process completed successfully
Installing '/usr/lib/php5/20090626/solr.so'
install ok: channel://pecl.php.net/solr-1.0.2
configuration option "php_ini" is not set to php.ini location
You should add "extension=solr.so" to php.ini


##Links
* https://bugs.php.net/bug.php?id=59028 [2011-07-06 18:52 UTC] mfonda@php.net
* http://derickrethans.nl/mongodb-and-solr.html