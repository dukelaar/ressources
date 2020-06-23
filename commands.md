* Extracting URL from JS file (gf could also be used)

cat file | grep -Eo "(http|https)://[a-zA-Z0-9./?=_-]*"*

curl http://host.xx/file.js | grep -Eo "(http|https)://[a-zA-Z0-9./?=_-]*"* 

* Having fun with tty

cat /dev/urandom > /dev/pts/1


