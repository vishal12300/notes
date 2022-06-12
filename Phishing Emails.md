### Below is a checklist of the pertinent information an analyst (you) is to collect from the email header:
* Sender email address
* Sender IP address
* Reverse lookup of the sender IP address
* Email subject line
* Recipient email address (this information might be in the CC/BCC field)
* Reply-to email address (if any)
* Date/time

Afterward, we draw our attention to the email body and attachment(s) (if any).

### Below is a checklist of the artifacts an analyst (you) needs to collect from the email body:
* Any URL links (if an URL shortener service was used, then we'll need to obtain the real URL link)
* The name of the attachment
* The hash value of the attachment (hash type MD5 or SHA256, preferably the latter)

## Phishing Email header, link, files analysis tools. 
* https://toolbox.googleapps.com/apps/messageheader/analyzeheader
* https://mha.azurewebsites.net/
* https://mailheader.org/
* https://ipinfo.io/
* https://urlscan.io/
* https://www.url2png.com/
* https://www.wannabrowser.net/
* https://talosintelligence.com/reputation
* https://app.any.run/
* https://www.hybrid-analysis.com/
* https://www.joesecurity.org/
* https://www.phishtool.com/ [Automation]


## Other Tools
* https://mxtoolbox.com/
* https://phishtank.com/?
* https://www.spamhaus.org/


### Per MITRE ATT&CK Framework, [Phishing](https://attack.mitre.org/techniques/T1598/) is classified as Technique ID 1598 (T1598), and it contains three sub-techniques.

##  Sender Policy Framework (SPF)
Sender Policy Framework (SPF) is used to authenticate the sender of an email. With an SPF record in place, Internet Service Providers can verify that a mail server is authorized to send email for a specific domain. An SPF record is a DNS TXT record containing a list of the IP addresses that are allowed to send email on behalf of your domain.

![image](https://assets.tryhackme.com/additional/phishing4/dmarcian-spf.png)



### How does a basic SPF record look like?
```
v=spf1 ip4:127.0.0.1 include:_spf.google.com -all
```
An explanation for the above record:

``` v=spf1 ``` -> This is the start of the SPF record

``` ip4:127.0.0.1 ``` -> This specifies which IP (in this case version IP4 & not IP6) can send mail

```include:_spf.google.com ``` -> This specifies which domain can send mail

```-all ``` -> non-authorized emails will be rejected


## DKIM (DomainKeys Identified Mail)
DKIM stands for DomainKeys Identified Mail and is used for the authentication of an email that’s being sent. Like SPF, DKIM is an open standard for email authentication that is used for DMARC alignment. A DKIM record exists in the DNS, but it is a bit more complicated than SPF. DKIM’s advantage is that it can survive forwarding, which makes it superior to SPF and a foundation for securing your email.

### How does a DKIM record look like?
```
v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAxTQIC7vZAHHZ7WVv/5x/qH1RAgMQI+y6Xtsn73rWOgeBQjHKbmIEIlgrebyWWFCXjmzIP0NYJrGehenmPWK5bF/TRDstbM8uVQCUWpoRAHzuhIxPSYW6k/w2+HdCECF2gnGmmw1cT6nHjfCyKGsM0On0HDvxP8I5YQIIlzNigP32n1hVnQP+UuInj0wLIdOBIWkHdnFewzGK2+qjF2wmEjx+vqHDnxdUTay5DfTGaqgA9AKjgXNjLEbKlEWvy0tj7UzQRHd24a5+2x/R4Pc7PF/y6OxAwYBZnEPO0sJwio4uqL9CYZcvaHGCLOIMwQmNTPMKGC9nt3PSjujfHUBX3wIDAQAB
```

An explanation of the above record:

``` v=DKIM1 ```-> This is the version of the DKIM record. This is optional. 

``` k=rsa ``` -> This is the key type. The default value is RSA. RSA is an encryption algorithm (cryptosystem).

```p= ```-> This is the public key that will be matched to the private key, which was created during the DKIM setup process. 


