---
aliases:
  - "Chapter 6 : Information Gathering"
---
# WHOIS Basics

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

# Quick Guide to Google Hacking

## 1. Discover Login Pages

# Find exposed login portals.
```
inurl:login
inurl:admin
intitle:"login page"
```

## 2. Search for File Types
# Locate specific file types like PDFs, spreadsheets, SQL backups, or log files.
```
filetype:pdf site:example.com
filetype:xlsx site:example.com
filetype:sql site:example.com
filetype:log
```

## 3. Exposed Configuration Files
# Search for exposed configuration or settings directories.
```
intitle:"index of" "config"
intitle:"index of" "settings"
```

## 4. Discover Sensitive Information
# Locate web pages containing sensitive keywords.

```
intext:"password"
intext:"username"
intext:"email"
```
## 5. Find Open Directories
# Expose directories that are not properly secured.
```
intitle:"index of /"
intitle:"index of" "parent directory"
```

## 6. Search for Admin Panels
# Locate admin or dashboard portals.
```
inurl:admin
inurl:dashboard
inurl:controlpanel
```

## 7. SQL Error Messages
# Identify sites vulnerable to SQL injection attacks by finding error messages.
```
intext:"sql syntax near" | intext:"sql syntax error"
```

## 8. Search by Specific Site
# Isolate results within a specific website or domain.
```
site:example.com "confidential"
site:example.com filetype:doc
```

## 9. Exposed Cameras
# Find unsecured IP cameras.
```
inurl:/view/index.shtml
inurl:"ViewerFrame?Mode="
```

## 10. Default Credentials
# Locate pages using default credentials.
```
inurl:"/phpMyAdmin/" "default password"
intitle:"phpMyAdmin" "login"
```

## 11. Search for Backup Files
# Expose backup files left on web servers.
```
inurl:backup filetype:zip
inurl:backup filetype:sql
```

## 12. Exposed Password Files
# Locate plaintext password files.
```
intitle:"index of" "password"
inurl:password filetype:txt
```

## 13. Publicly Accessible Emails

# Find email addresses for phishing or reconnaissance.
```
site:example.com intext:"@example.com"
```

## 14. Discover Vulnerable Web Applications
# Find websites running specific CMSs (e.g., WordPress, Joomla).
```
inurl:wp-admin | inurl:wp-login
intitle:"Joomla! Administration Login"
```

## 15. Search for Databases
# Identify exposed database management systems.
```
inurl:"phpMyAdmin" | inurl:"/dbadmin/"
inurl:"/db/" | intext:"mysql dump"
```

## 16. Detect Login Credentials in Git Repositories
# Locate sensitive `.env` files that may expose credentials.
```
intext:"DB_PASSWORD" filetype:env
intext:"DB_USER" filetype:env
```

## 17. Locate Sensitive Directories
# Find directories meant to be private
```
inurl:/private/
inurl:/conf/
inurl:/secure/
```

## 18. Search for Unsecured Portals
# Locate client portals that may not be secured.
```
inurl:"portals/" intitle:"client"
```

`trivera:$apr1$A0vSKwao$GV3sgGAj53j.c3GkS4oUC0`

6.2.4 Open Source Code

- [GitHub](https://github.com/)
- [GitHub Gist](https://gist.github.com/)
- [GitLab](https://about.gitlab.com/)
- [SourceForge](https://sourceforge.net/)

## 6.3.1. DNS Enumeration
- **NS**: Nameserver records contain the name of the authoritative servers hosting the DNS records for a domain.
- **A**: Also known as a host record, the "_a record_" contains the IPv4 address of a hostname (such as www.megacorpone.com).
- **AAAA**: Also known as a quad A host record, the "_aaaa record_" contains the IPv6 address of a hostname (such as www.megacorpone.com).
- **MX**: Mail Exchange records contain the names of the servers responsible for handling email for the domain. A domain can contain multiple MX records.
- **PTR**: Pointer Records are used in reverse lookup zones and can find the records associated with an IP address.
- **CNAME**: Canonical Name Records are used to create aliases for other host records.
- **TXT**: Text records can contain any arbitrary data and be used for various purposes, such as domain ownership verification.

host www.megacorpone.com
host -t mx megacorpone.com
host -t txt megacorpone.com
dnsrecon -d megacorpone.com -t std

nc -nvv -w 1 -z 192.168.50.152 3388-3390
nc -nv -u -z -w 1 192.168.50.149 120-123