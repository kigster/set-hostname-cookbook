# Set Hostname

This simple cookbook sets the hostname on a given host using the `node.name` as the default name, and appending any domain, if provided, for the fully qualified domain name of the host.

It also populates the file `/etc/hosts` file.

## Attributes

You can set the following attributes:

```ruby
node.normal['set-hostname']['name']           = 'foo' 
node.normal['set-hostname']['domain']         = 'bar.com'
node.normal['set-hostname']['ip']             = '1.2.3.4'
node.normal['set-hostname']['hosts-file']     = '/etc/hosts' 
```

This will result in the hostname set to `foo.bar.com` and the IP address in the `/etc/hosts` file will be `1.2.3.4`. 

### Default Attributes

The cookbook only requires that you set the domain portion of the name. 

In that case, the actual hostname portion is inferred from the `node.name`, and the IP address is taken from `node['ipaddress']`.

If you do not provide the domain name, the host is configured without the FQDN.

### Contributing

To contribute, please [fork](https://github.com/kigster/set-hostname-cookbook/fork) the cookbook and submit a pull request.

## License

MIT License, full text is in the [LICENSE.md](LICENSE.md) file.

## Authors

 * Konstantin Gredeskoul (current maintainer)
 * Eric Saxby