=====================================================
 Link - Opera Link PHP demo
=====================================================

This is a simple sample php page that will retrieve
a user's SpeedDials and show them as a web page.

License
=======
The source code included in this distribution is distributed under the
BSD license:

Copyright © 2010, Opera Software
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

* Redistributions of source code must retain the above copyright
  notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright
  notice, this list of conditions and the following disclaimer in the
  documentation and/or other materials provided with the distribution.
* Neither the name of Opera Software nor the names of its contributors
  may be used to endorse or promote products derived from this
  software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

Instructions
============

INSTALLING PHP ON UBUNTU/DEBIAN

Skip this part if you already have access to a web server that can run PHP.

$> sudo apt-get install apache2
$> sudo apt-get install php5 php5-dev php-pear
$> sudo a2enmod php5
$> sudo mkdir -p /var/www/link
$> sudo chown www-data:www-data /var/www/link      

INSTALLING OAUTH PHP LIB

If you do not control your server, you will need to ask your administrator
to install this module.

$> sudo apt-get install build-essential libcurl-devel
$> sudo pecl install oauth
$> cat "extension=oauth.so" > /etc/php5/apache2/conf.d/oauth.ini
$> sudo apache2ctl restart

The manual is here http://www.php.net/manual/en/book.oauth.php

ENABLE PHP LOGGING IF YOU LIKE

If you do not control your server, you will need to ask your administrator
to install this module.

Edit /etc/php5/apache2/php.ini and uncomment the error_log line
error_log = /var/log/php_errors.log

$> touch /var/log/php_errors.log
$> chown www-data:www-data /var/log/php_errors.log
$> sudo apache2ctl restart

CHECK OUT THE EXAMPLE

$> cd ~ 
$> git clone git://github.com/operasoftware/PhpOperaLink
$> cd PhpOperaLink

Copy the code to your web server
$> cp -R *.php css /var/www/link/

REGISTER YOUR APP ON auth.opera.com/service/oauth

Choose "Web Application"
For the callback URL, choose 127.0.0.1/link/index.php (or use the name of
the server that you are deploying this on.)
Edit config.php and put in the key and secret that you are granted

TRY IT
Visit http://127.0.0.1/link/index.php (or the name of the server that you
are deploying this on.)
Insert Opera Link username/password when asked

For debugging, you may want to clear data in your PHP session between
each reload. Preferences->Cookies->Manage Cookies-> search <name of server> and
delete the PHPSESSID cookie.

KNOWN BUGS
==========
none
