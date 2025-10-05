# headers 

```
X-URL-Request: /internal/admin
x-original-url : /admin
x-forwarded-port: 9000
x-forwarded-for: 127.0.0.1
x-forwarded-proto: http
X-HTTP-Method-Override: PUT
Next-Router-State-Tree: %5B%22%22%2C%7B%22children%22%3A%5B%22en%22%2C%7B%22children%22%3A%5B%22search%22%2C%7B%22children%22%3A%5B%5B%22search%22%2C%22hello%22%2C%22d%22%5D%2C%7B%22children%22%3A%5B%22__PAGE__%22%2C%7B%7D%5D%7D%5D%7D%5D%7D%2Cnull%2Cnull%2Ctrue%5D%7D%5D
Origin: http://localhost:3000
host: kwk4ufof0q3hdki5e46mpchscjia69uy.oastify.com
connection: close
cache-control: no-cache, no-store, max-age=0, must-revalidate
cookie: ; undefined
next-action: 15531bfa07ff11369239544516d26edbc537ff9c
rsc: 1
user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.6312.58 Safari/537.36
vary: RSC, Next-Router-State-Tree, Next-Router-Prefetch, Next-Url
x-action-redirect: /login
x-action-revalidated: [[],0,0]
x-forwarded-for: ::ffff:127.0.0.1
x-forwarded-host: kwk4ufof0q3hdki5e46mpchscjia69uy.oastify.com
x-forwarded-port: 3000
x-forwarded-proto: http
accept: */*
accept-language: *
sec-fetch-mode: cors
accept-encoding: gzip, deflate
Host: attacker.example.test
X-Forwarded-Host: attacker.example.test
X-Forwarded-For: 203.0.113.45
X-Forwarded-Proto: https
X-Url-Scheme: https
X-Forwarded-Scheme: https
Forwarded: host=attacker.example.test;proto=https
X-Forwarded-Port: 443
X-Forwarded-Prefix: /prefix
X-Original-URL: /some/original/path?x=1
X-Rewrite-URL: /rewritten/path
X-Original-Host: attacker.example.test
X-ProxyHost: attacker.example.test
X-Host: attacker.example.test
X-Forwarded-Server: proxy-01.example.net
X-Real-IP: 203.0.113.45
X-Original-URI: /original/uri
X-Forwarded-Uri: /forwarded/uri
X-Request-Uri: /request/uri
Referer: https: //attacker.example.test/page
Origin: https: //attacker.example.test
Cookie: session=TESTSESSIONID;other=1
Authorization: BearerTEST_TOKEN
X-Requested-With: XMLHttpRequest
Accept: application/json
Accept-Encoding: gzip,deflate
Accept-Language: en-US,en;q=0.9
Date: Sun, 05 Oct 2025 06:06:58 GMT
Content-Type: application/json
Connection: keep-alive
Host: app.example.com
CF-EW-Via: 15
CDN-Loop: cloudflare; loops=1; subreqs=1
X-Forwarded-Proto: https
CF-Ray: 989abc6c6cc6480b-BOM
CF-Cache-Status: DYNAMIC
Accept-Encoding: gzip
Accept-Language: en-US,en;q=0.5
Accept: */*
Access-Control-Allow-Origin: https://appxexample.com
Cookie: dajs_user_id=%22ML992HXXXXXB%22; 
Referer: https://app.example.com/dashboard/
Strict-Transport-Security: max-age=631152000; includeSubDomains; preload
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:143.0) Gecko/20100101 Firefox/143.0
Vary: origin, accept-encoding
access-control-allow-credentials: true
apollographql-client-name: dashboard
cdn-auth-header-status: present_and_match
cdn-client-ip: 106.222.215.181
cf-connecting-ip: 106.222.215.181
cf-ipcountry: IN
cf-visitor: {"scheme":"https"}
cf-worker: app.example.com
client-ip: 106.222.215.181
origin: https://appxexample.com
priority: u=4
sec-fetch-dest: empty
sec-fetch-mode: cors
sec-fetch-site: same-origin
traceparent: 00-68e20b02000000007ce859d341ebb987-7ce859d341ebb987-00
tracestate: dd=s:-1;p:7ce859d341ebb987
x-allow-cookies: ,C0001,C0002,C0003,C0004,
x-amzn-trace-id: Root=1-68e20b02-4a654ffd6ed887b233dd1301
x-b3-sampled: 0
x-b3-spanid: 6327acd188e00ade
x-b3-traceid: 68e20b02000000007ce859d341ebb987
x-block-cookies: true
x-block-mesh-src-region: us-west-2
x-body-hash: f8953d40eccc0ec553e8cc3e3e181356
x-cdn-bot-score: 83
x-cdn-geoip-asnum: 24560
x-cdn-geoip-continent: AS
x-cdn-geoip-iso-one: IN-MP
x-cdn-geoip-iso-two: IN-444
x-cdn-ip-threat-score: 0
x-cdn-ja3-hash: d7a2543716f784e8de73ffe3f7f6234b
x-cdn-lat: 23.25469
x-cdn-lon: 77.40289
x-cdn-trace-id: CDN-45175a40-b18c-4d0d-a95e-9fbdcf9ca375
x-cdn-verified-bot: false
x-cookie-count: 58
x-cookies-hash: e89a606f86a5fb6a90c38abd2c5d02d027140cce5346c70adc034066051b615f
x-csrf-token: n6bGb25YZpjoXMS94vvhKwpPZNSmpPQ3mvn7GYg3D9E
x-datadog-parent-id: 7144869349791107806
x-datadog-sampling-priority: -1
x-datadog-tags: _dd.p.tid=68e20b0200000000
x-datadog-trace-id: 9000542619178875271
x-envoy-decorator-operation: /1p/graphql/**
x-forwarded-client-cert: By=spiffe://production.ski.example.com/graphql-gateway;Hash=0529795055035179f1c0e6e2d8abeb01f320122d55dcced426752e775b06ea03;Cert="-----BEGIN%20CERTIFICATE-----%0AMIIDLzCCAtSgAwIBAgIRAPnc67%2B5rAZxtTeA0Z%2FmH5MwCgYIKoZIzj0EAwIwYDEL%0AMAkGA1UEBhMCVVMxEzARBgNVBAoMCkJsb2NrLCBJbmMxKDAmBgNVBAMMH1NLSSBB%0AV1MgTmF0aXZlIENBIHByb2R1Y3Rpb24gRzAxEjAQBgNVBAcMCXVzLWVhc3QtMTAe%0AFw0yNTEwMDMxNTQ3MDBaFw0yNTExMDIwMzQ1MDRaMEMxQTA%2FBgNVBAMTOFNxdWFy%0AZS1BV1MtcHJvZHVjdGlvbi5za2kuc3F1YXJlY2xvdWRzZXJ2aWNlcy5jb20tdHJh%0AY29uMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA3HpfqVz4xMj09UZi%0AEHPHbF7Do732tdVQ8bbLs%2F6QdtqA%2F9%2BEnPtrBlH62JrazTv0bLWTaOeIpP8HIAP%2B%0AvBzW3NTuN6X5I51SAjeGGth84yT28uFuU8X%2BXgqtO3ulC7iBtx0wsxvXjMNr%2BIei%0Ae5ZfRZSMblwVTtpCvUI4D4ovooTranySTMlS09N%2B6fOgmcfUUEMjx4BDYacABAJe%0AfCyM5US%2BlAybB8CTzYgRgImFMgaEJJqICUyH4MiKQYcY0jUvuyIuSUNYpaBdg4%2FD%0AGjbjxmFfNgeTN4HdD9DhwpeQu9L2QVEqtqmGAjTT7jnvcDuSpg0v8YGyz89rAIvd%0ArSH%2BmQIDAQABo4HAMIG9MEEGA1UdEQQ6MDiGNnNwaWZmZTovL3Byb2R1Y3Rpb24u%0Ac2tpLnNxdWFyZWNsb3Vkc2VydmljZXMuY29tL3RyYWNvbjAJBgNVHRMEAjAAMB8G%0AA1UdIwQYMBaAFMGl%2F3xrOtgSFgx8PWuMOeX5r9F6MB0GA1UdDgQWBBR7rtuVn6LK%0A5Xcd66lSctuRCUSsTjAOBgNVHQ8BAf8EBAMCBaAwHQYDVR0lBBYwFAYIKwYBBQUH%0AAwEGCCsGAQUFBwMCMAoGCCqGSM49BAMCA0kAMEYCIQCat9M1NsKMyQ%2F8geRxIKs5%0AShuDWKoLBpsyZtDF4VoLQQIhANsBNzJd%2FPiK81%2Fvax3w%2BnqacKBxqgL1UxaVf7KR%0AW0e%2F%0A-----END%20CERTIFICATE-----%0A"
x-forwarded-for: 106.222.215.181
x-forwarded-port: 443
x-multipass-credential: CAESowUthjkcRm89CklqIP9Hm3cGKreKI-nHmDxqh8zL2--bbztMkQ8EtaFqg4dj6ulssk6dwVqUF_bx7nlMdKtrPWECSN6ieX1hn7R-Fcw2Vf1rIPZXxd8fCW8llp5T2-lGOPH4aQeSJFXb0lZBT5Eme0tXv-74l_Gd9HlA0t_-LtPlboJTuAYcVy2vkoSo9FMfXC2-kHmjHORg1O_eFhkutdssoIj2w6EiDVie0_3TEeQ-HmXzRFTXVr0Dl6bhDo8kOqAoCUrCCZOMIkY_fI7-f4UTtzYK1cwmh12WbXM3q6BW_ezFLjT4NP95clWUzGLBy-j7gvy8c76OAZi-S-FZIO7qQ0WAAcW0gpebM4gBFpABAZoBhgEKEFRNYW9HTDZSbi1yai1sQkkaOAoNTUxXOVZNVkY1R01ETRIn____-_____________________________________________8_IjgKDUxWSkFYVk1YVEpQQ0USJ_____v_____________________________________________P6IBBWVuLVVTqgEMQXNpYS9Lb2xrYXRhsgFAOGIyYWVmMWNlOTRiZTUzYjNlZGFmOTgwNDdlMmMyMzAxMmEzYzlhYWUxYzk5MmE0ODZkN2EyNzI4ZTEyMjJiNNoBAJgCAKICbwojCiH8mZ_f2eef_5_9_fifTw3_____g48__5__nqU_AD7A_A8SIwoh_Jmf39nnn_-f_f34n08N_____4OPP_uf_56lPwA-wPwPGiMKIfyZnt_Z558_nu09-JtIDP___5-Djz_7n_-epTkAPgD8DagCALoCK242YkdiMjVZWnBqb1hNUzk0dnZoS3dwUFpOU21wUFEzbXZuN0dZZzNEOUXQAgDgAgA
x-real-bot-score: 83
x-request-headers-count: 39
x-request-headers-hash: b0935648fb487da0ea4b31e0d8f09e00ce8e4b601ef8f9957b6ff782d5476ccf
x-request-id: 30ceebfe-bdb5-4fbf-8e4b-c17970ccad90
x-savt: a1198edc-06e1-4bd8-867b-fda6c410c702
x-sip-selected-merchant: MLW9VMVF5GMDM
x-sip-session-id: 8b2aef1ce94be53b3edaf98047e2c23012a3c9aae1c992a486d7a2728e1222b4
x-speleo-trace-id: CDN-45175a40-b18c-4d0d-a95e-9fbdcf9ca375
x-sq-caller-app-name: tracon
x-sq-caller-spiffe-id: spiffe://production.ski.example.com/tracon
x-sq-dc: aws
x-sq-envoy-safe-auth-decision: AUTHORIZED
x-sq-istio-migration-ingress-proxy: sq-envoy
x-sq-istio-migration-ingress-region: us-west-2
x-sq-multipass-csrftoken: n6bGb25YZpjoXMS94vvhKwpPZNSmpPQ3mvn7GYg3D9E
x-sq-multipass-http-code: OK
x-sq-peer-spiffe-id: spiffe://production.ski.example.com/tracon
x-sq-region: us-west-2
x-sxuxre-tls-version: TLSv1.2
Set-Cookie: __cf_bm=LNBsvd1zIXytPWxmxk8tJlspTwd0kFAOFUt2I2DaGm0-1759644418-1.0.1.1-gyAtFOYR4g9D3J8St2qw8sgJxe8646HKEhA35yZ_Qx2Lrz6byiXX4GPHCN6lKFjfjWDO_eQMPoak7Rqmw1AcQJ6Qwqbg1eHrO1NYEYA6syo; path=/; expires=Sun, 05-Oct-25 06:36:58 GMT; domain=.app.example.com; HttpOnly; Secure; SameSite=None
Server: cloudflare
Content-Length: 166
```
