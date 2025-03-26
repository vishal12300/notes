#### Next.js between 13.5.1 and 14.2.9 => CVE-2024-46982

[https://zhero-web-sec.github.io/research-and-things/nextjs-cache-and-chains-the-stale-elixir](https://zhero-web-sec.github.io/research-and-things/nextjs-cache-and-chains-the-stale-elixir)


# Headers 
#### Try this headers in the request and Observer the Changes in the Response headers. 
```
x-now-route-matches: 1
X-middleware-prefetch: 1
RSC: 1
```

```
/_next/data/{buildID}/targeted-page.json

https://www.example.com/?__nextDataReq=1
```

------------------------------

## SSRF 

[https://www.assetnote.io/resources/research/digging-for-ssrf-in-nextjs-apps](https://www.assetnote.io/resources/research/digging-for-ssrf-in-nextjs-apps)
