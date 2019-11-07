# org.freedesktop.Sdk.Extension.php73

This extension adds PHP support to Flatpak.

PHP installs to `/usr/lib/sdk/php73` inside the sandbox.

Example Visual Studio Code Configuration

```json
"php.validate.executablePath": "/usr/lib/sdk/php73/bin/php",
"php.executablePath": "/usr/lib/sdk/php73/bin/php",
```

Includes

* [php](https://php.net/) (7.3.11)
* [composer](https://github.com/composer/composer) (1.9.1)
* [apcu](https://pecl.php.net/package/APCu) (5.1.18)
* [xdebug](https://xdebug.org/) (2.8.0)

Each Flatpak can have its own custom php configuration files.
e.g. for Visual Studio Code
`~/.var/app/com.visualstudio.code/config/php/7.3/ini/my-custom.ini` or `/var/config/php/7.3/ini/my-custom.ini` from a sandboxed shell.

Global composer installs are limited to the Flatpak they were installed in.

#### Troubleshooting
`/usr/bin/env: ‘php’: No such file or directory`

Run `. /usr/lib/sdk/php73/enable.sh` or add `/usr/lib/sdk/php73/bin` to your $PATH.

#### Modules

```bash
bash-5.0$ php -m
[PHP Modules]
apcu
bcmath
bz2
calendar
Core
ctype
curl
date
dom
exif
fileinfo
filter
ftp
gd
gettext
hash
iconv
intl
json
ldap
libxml
mbstring
mysqli
mysqlnd
openssl
pcntl
pcre
PDO
pdo_mysql
pdo_pgsql
pdo_sqlite
Phar
posix
pspell
readline
Reflection
session
SimpleXML
sockets
sodium
SPL
sqlite3
standard
sysvmsg
sysvsem
sysvshm
tokenizer
wddx
xdebug
xml
xmlreader
xmlrpc
xmlwriter
xsl
zip
zlib

[Zend Modules]
Xdebug
```
#### Build
```bash
flatpak-builder --repo repo _build org.freedesktop.Sdk.Extension.php73.json --force-clean
```
