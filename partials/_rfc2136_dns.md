[RFC 2136](https://www.rfc-editor.org/rfc/rfc2136) is intended for use with DNS providers not otherwise supported by Cloud 66. Your provider needs to support RFC 2136, and ideally needs a good help document to walk you through the set up.

In order to add your RFC 2136 DNS to Cloud 66 you need to create an `.ini` file containing the credentials **required by your provider**. A typical file would look similar to this:

```bash
# Target DNS server (IPv4 or IPv6 address, not a hostname)
dns_rfc2136_server = 192.0.2.1
# Target DNS port
dns_rfc2136_port = 53
# TSIG key name
dns_rfc2136_name = keyname.
# TSIG key secret
dns_rfc2136_secret = 4q4wM/2I180UXoMyN4INVhJNi8V9BCV+jMw2mXgZw/CSuxUT8C7NKKFs AmKd7ak51vWKgSl12ib86oQRPkpDjg==
# TSIG key algorithm
dns_rfc2136_algorithm = HMAC-SHA512
```

Your own provider *may give the keys different names* or require a different set of keys. Please be sure to follow their instructions carefully. 

Once you have all the credentials, you can add RFC2136 to your Cloud 66 account by uploading your `.ini` file ([see above](#set-up-a-dns-provider)).