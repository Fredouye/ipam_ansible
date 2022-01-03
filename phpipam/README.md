This role is using phpIPAM's REST API, described here : https://phpipam.net/api/api_documentation/

By default, The API can only be used when accessed with HTTPS scheme.
You can allow HTTP access (if phpIPAM is runing behind a reverse proxy, for example) by adding this to config.dist.php :

```php
/**
 * Allow API calls over HTTP (security = none)
 *
 * @var bool
 */
$api_allow_unsafe = true;
```

You then need to enable API access, through Administration -> phpIPAM settings -> API : ON

Once enabled, create a new key through Administration -> API -> Create API key

```php
App id : Ansible
App permissions : Read / Write
App security : SSL with App code token
```

You then have to add the "App code" in your Ansible's variables :

```yml
phpipam_url: https://ipam.mydomain.com
phpipam_api_app: Ansible
phpipam_token: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

For every phpIPAM's subnet, you have to declare a gateway and enable "Show as name".

For every host you want to set/get an IP address, you have to declare its subnet :

```yaml
vm_network: "VM Network"
```

If an IP address has already been declared, for a host, it will be fetched from phpIPAM. Otherwise, the role will reserve an IP address.
When running the role, you'll get 3 variables for each host :

```
vm_ip: 192.168.3.101
vm_netmask: 255.255.255.0
vm_gateway: 192.168.3.254
```

These variable can be displayed by enabling debug mode :

```yaml
debug: true
```


