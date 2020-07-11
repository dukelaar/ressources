* Extracting URL from JS file (gf could also be used)

```
cat file | grep -Eo "(http|https)://[a-zA-Z0-9./?=_-]*"*

curl http://host.xx/file.js | grep -Eo "(http|https)://[a-zA-Z0-9./?=_-]*"* 
```

* Having fun with tty

```
cat /dev/urandom > /dev/pts/1
```

* Scanning subdomains for HTTP with @pdchaos httpx & then scanning it again for specific URL with the use of @TomNomNom's unfurl. #bugbounty

```
cat domains.txt | httpx | unfurl format "%s://%d%p/interesting_url"  | httpx -title -status-code -verbose
```

* Recherche shodan 

```
shodan search org:"Target" http.favicon.hash:116323821 --fields ip_str,port --separator " " | awk '{print $1":"$2}' | while read host do ;do ffuf -u http://$host/FUZZ -mc 200 -w spring-boot.txt ;done
```

* Recherche de vulnérabilités et exploitation nuclei

```
shodan search org:"Target" http.favicon.hash:116323821 --fields ip_str,port --separator " " | awk '{print $1":"$2}' | httprobe | nuclei -t workflows/springboot-pwner-workflow.yaml
```

https://medium.com/@dwi.siswanto98/weaponizes-nuclei-workflows-to-pwn-all-the-things-cd01223feb77
