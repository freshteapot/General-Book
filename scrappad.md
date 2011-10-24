#Scrappad

This is like "in-progress" files.

* Not finished
* In progress
* Dont trust

***
---------

After creating this little command. You are able to successfully send commands to different "tty".
http://www.humbug.in/2010/utility-to-send-commands-or-data-to-other-terminals-ttypts/


---------
solr


##Edit solrconfig.xml

 <indexDefaults>
   <!-- Values here affect all index writers and act as a default unless overridden. -->
    <useCompoundFile>true</useCompoundFile>

    <mergeFactor>5</mergeFactor>


lsof | grep 'java' | wc -l



su www-data -c "php extension/ezfind/bin/php/ezsolroptimize.php -s SITE_NAME"

This is after we did some changes.

root@xena:/var/cache/ezfind# lsof | grep 'java' | grep '/var/cache/ezfind/gan_aschehoug' | wc -l
95
root@xena:/var/cache/ezfind# lsof | grep 'java' | grep '/var/cache/ezfind/gan_aschehoug' | wc -l
13

Michael suggests to make sure the numbers are impressive by doing this before making changes.

Sadly we saw all have similiar changes. Not what we were hoping for.

We decided after Michael suggested to revert our changes and then just optimize all sites.


find /var/www/ez_live/ -maxdepth 1 -type d -printf '%f\n' | grep -v '\.' | awk '{cmd="cd /var/www/ez_live/"$0"/live && su www-data -c \"php extension/ezfind/bin/php/ezsolroptimize.php -s "$0"_admin\"";system(cmd);}'



root@xena:/var/cache/ezfind# lsof | grep 'java' | wc -l
331



http://humorum:8983/solr/admin/cores?action=UNLOAD&core=aperitif_4_4

http://humorum:8983/solr/admin/cores?action=RELOAD&core=auf_jegstemmer

## Searched for
* solr useCompoundFile 
* solr failing due to too many files open
* solr Lock obtain timed out
* how to reload solrconfig.xml


## Links
* http://wiki.apache.org/solr/CoreAdmin
* http://wiki.apache.org/solr/SolrPerformanceFactors

---------
<html>
<body>
<pre>Hello, eZ has been upgraded</pre>
<!-- #clue
Y2hhbmdlIHRoZSBkZWZhdWx0IHJld3JpdGUgcnVsZSBpbiBhcGFjaGUgdG8gbWFrZSB0aGlzIHdv
cmsgYWdhaW4K
-->
</body>
</html>



find /etc/apache2/sites-enabled/ -name 'ez.*' | sed -E 's/.+ez\.([0-9]+\.[0-9]+)/\1/'
After a quick who.is.

http://who.is/encripto.no

Lets start with the more cryptic and speculative aspect:

mikerinos@hotmail.com

May have come from:
http://tr.wikipedia.org/wiki/Mikerinos_Piramidi (Turkish)
 
http://en.wikipedia.org/wiki/Pyramid_of_Menkaure (English)


Organisation Id:

Armed with the organisation Id

http://w2.brreg.no/enhet/sok/detalj.jsp;jsessionid=SWnnTKrT1ty4Tmd0QwkQ4rNmTsrcnQY9JYvgmTBZqKYTMRpntysC!-507924851!-1892467537?orgnr=996240630


Further to that, cross referencing the info added we can look the people up who spammed us.

http://www.1881.no/?Query=4747259402&qt=8

Juan Jose Gyelfo Borrajo – 912 40 380 
Richard Eidsvigs veg 31, 6006 Ålesund


Ingrid Bentzen – 472 59 402 
Richard Eidsvigs veg 31, 6006 Ålesund

Its curious a new company would do something like this. It seems such a bad approach.

Finally, do you think he feels his non Norwegian name will hinder him in Business in Norway as he has dropped Borrajo from his "internet persona".


A side point

HEAD encripto.no

200 OK
Cache-Control: no-store, no-cache, must-revalidate, post-check=0, pre-check=0
Connection: close
Date: Tue, 16 Aug 2011 08:42:27 GMT
Pragma: no-cache
Via: 1.1 varnish
Age: 0
Server: Apache
Content-Length: 9120
Content-Type: text/html
Expires: Thu, 19 Nov 1981 08:52:00 GMT
Client-Date: Tue, 16 Aug 2011 08:42:27 GMT
Client-Peer: 193.202.110.241:80
Client-Response-Num: 1
Set-Cookie: PHPSESSID=dnlggi5q4okeqnhb9j9mus7lj3; path=/
X-Powered-By: PHP/5.3.6
X-Varnish: 839828637

For a security consultant it seems strange that he has left the "Powered By" header, as it gives attackers a clue.


Further digging, we are able to find who the ip address belongs to.

one.com
https://apps.db.ripe.net/dbweb/search/query.html;jsessionid=7B54EA9C1EE38515F6CB5248CAE06A51.node2

To which we an email address for reporting spam.

abuse@one.com


We can go even further and use google maps to see the persons home.
---------









1) Header locations - let it be known it is a redirect
2) What is the default behaviour of apache rewrite rules. = sensitive, so I support strpos for that reason.

strpos vs stripos

Side point, speed complaints of stripos and strpos is a little pointless when the overal speed of the system is considered.


http://httpd.apache.org/docs/2.0/mod/mod_rewrite.html



searched for:
apache rewrite rules

http codes



Links:
http://httpd.apache.org/docs/2.0/mod/mod_rewrite.html - Reference worth reading for background understanding

http://www.addedbytes.com/download/mod_rewrite-cheat-sheet-v2/png/ - Awesome cheatsheet

http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html - Long Detailed list of http codes.



---------
cd /var/lib/apt/lists
gpgv --keyring /etc/apt/trusted.gpg http://debian-multimedia.org/dists/squeeze/Release.gpg \

gpgv - Verify OpenPGP signatures
man gpgv