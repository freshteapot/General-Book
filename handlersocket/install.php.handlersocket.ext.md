#Installing PHP-Handlersocket.

##Project Home

* http://code.google.com/p/php-handlersocket/


- The spelling on the download file is wrong.

```
curl "http://php-handlersocket.googlecode.com/files/php-handelrsocket-0.3.1.tar.gz" > php-handlersocket-0.3.1.tar.gz
tar zxf php-handlersocket-0.3.1.tar.gz
cd handlersocket
./configure --disable-handlersocket-hsclient
make
make test
make install
```



I had to build with --disable-handlersocket-hsclient as it complained about:

* configure: error: C++ preprocessor "/lib/cpp" fails sanity check
