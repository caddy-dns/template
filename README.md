Dinahosting module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with [Dinahosting](https://dinahosting.com).

## Caddy module name

```
dns.providers.dinahosting
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "dinahosting",
				"username": "YOUR_PROVIDER_USERNAME",
				"password": "YOUR_PROVIDER_PASSWORD"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns dinahosting {
		username "OUR_PROVIDER_USERNAME"
		password "YOUR_PROVIDER_PASSWORD"
	} 
}
```

```
# inside domain block
example.com {
	tls {
		dns dinahosting {
			username "OUR_PROVIDER_USERNAME"
			password "YOUR_PROVIDER_PASSWORD"
		} 
	}	
}

```
