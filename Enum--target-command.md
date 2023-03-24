## Commands

```

amass enum -brute -active -d domain.com -o amass-output.txt

cat amass-output.txt | httprobe -p http:81 -p http:3000 -p https:3000 -p http:3001 -p https:3001 -p http:8000 -p http:8080 -p https:8443 -c 50 | tee online-domains.txt

cat new-output.txt | anew old-output.txt | httprobe

cat amass-output.txt | dnsgen - | httprobe

cat domains-endpoints.txt | aquatone
```
