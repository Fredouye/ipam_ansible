This role is using EfficientIP SOLIDserver's REST API.

You need to provide your URL and credentials :

```yaml
ipam_url: https://myipam.domain.com
ipam_username: myusername
ipam_password: toto12345
```

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

You'll get this result :

```bash
TASK [phpipam : ***Debug*** Display current IP address] ********************************************************************************************
ok: [rocky8-vmware1] => {
    "msg": [
        "**** Existing record ****",
        "subnet     : VM Network (192.168.3.0/24)",
        "hostname   : rocky8-vmware1",
        "IP address : 192.168.3.2",
        "gateway    : 192.168.3.254",
        "netmask    : 255.255.255.0"
    ]
}
```
