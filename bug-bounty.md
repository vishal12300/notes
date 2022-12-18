# Subdomain Enumerations

```
https://crt.sh/?q=%25.target.com
https://securitytrails.com/list/apex_domain/target.com
https://www.shodan.io/search?query=Ssl.cert.subject.CN%3A%22target.com%22

```

#### shodan.io 
```
Ssl.cert.subject.CN:"target.com"
```

#### Tools
 
* Sublist3r
* Amass
* Subfinder
* Assetsfinder (tomnomnom)
* [https://jldc.me/anubis/subdomains/att.com](https://jldc.me/anubis/subdomains/att.com)
* GitHub - iamthefrogy/frogy
* GitHub - Cyber-Guy1/domainCollector
* https://gitlab.com/prawps/ohdns

-----------

# Port Scanning

#### Tools

* nmap
* masscan
* naabu

#### Commands tips

```
naabu -list sub-list.txt -top-ports 1000 -exclude-ports 80,443,21,22,25 -o ports.txt
naabu -list sub-list.txt -p -  -exclude-ports 80,443,21,22,25 -o ports.txt

```

---------------

# COLLECTING URLS ENDPOINTS

```
https://urlscan.io/search/#target.com
https://web.archive.org/cdx/search/cdx?url=*.target.com&fl=original&collapse=urlkey

```

#### Google dorking
```
site:target.com
```

#### Bing dorking

```
site:target.com
```

--------------

# SEARCH FOR SOURCES/BACKUP FILES

#### Tip:

```
orwa.iwcon.com
orwa.iwcon.com/orwa.zip - iwcon.zip – admin.zip – backup.zip
orwa. iwcon.com/orwa/orwa.zip - wicon.zip – admin.zip – backup.zip
orwa. iwcon.com/iwcon/orwa.zip - iwcon.zip – admin.zip – backup.zip
orwa. iwcon.com/admin/orwa.zip - iwcon.zip – admin.zip – backup.zip
```

#### Tools
* https://github.com/musana/fuzzuli


------------------

# Credential Leakage and Secret Sisclosure

#### Try Searching For Leakes On 
```
gist.github.com
Gitlab.com
```

#### Leaked Credentials On Google and In Google Sheets/Groups

```
site:docs.google.com/spreadsheets "company name“
site:groups.google.com "company name"
```


