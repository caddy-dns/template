ddnss module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with ddnss (https://ddnss.de).

## Caddy module name

```
dns.providers.ddnss
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "ddnss",
				"api_token": "YOUR_DDNSS_API_TOKEN",
				"username": "YOUR_DDNSS_USERNAME", // Optional username
				"password": "YOUR_DDNSS_PASSWORD"  // Optional password
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns ddnss ...
}
```

```
# one site
tls {
	dns ddnss ...
}
```
