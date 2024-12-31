---
aliases:
  - "Chapter 6 : Information Gathering"
---
WHOIS Basic

```
whois megacorpone.com -h 192.168.50.251
```

Lists the nameservers, which can sometimes hint at associated subdomains.

```
whois example.com | grep -i 'Name Server'
```

Combine `whois` and `dig` for deeper insights:

```
whois example.com && dig example.com any
```