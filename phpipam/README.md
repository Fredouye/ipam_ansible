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

