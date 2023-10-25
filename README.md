Collection of Ansible roles to be used with several [IPAM](https://en.wikipedia.org/wiki/IP_address_management) services :
- [efficient_ip](https://github.com/Fredouye/ipam_ansible/tree/main/efficient_ip) : EfficientIP SOLIDserver
- [Netbox](https://github.com/Fredouye/ipam_ansible/tree/main/netbox) : Netbox's IPAM
- [phpipam](https://github.com/Fredouye/ipam_ansible/tree/main/phpipam) : phpIPAM.

If an IP address is already declared for a host, these roles will get it and affect to a variable.
Otherwise, they will reserve an new IP address.
