DNSimple Dynamic DNS
====================

DNSimple Dynamic DNS is a script to update the IPv4 and IPv6 addresses for a particular record in DNSimple using either the public IP addresses or interface IP addresses for a computer.


Usage
-----

Edit the /etc/default/ddns file to fill in the parameters like below.

```
token='0123456789abcdefghijklmnopqrstuv'
account=1010
zone='example.com'
arecord=5
aaaarecord=6

ifip=false
```

The `token` parameter is your API token obtained from "Account" -> "API tokens" in the DNSimple interface. The `zone` parameter is the DNS zone, such as 'example.com'. The `arecord` and `aaaarecord` parameters are the DNSimple id of the record to update. The `ifip` parameter indicates whether the script should get the IP addresses from the primary internet interface or from an external service (icanhazip.com). You probably want `ifip=false` unless you know what you are doing.

```
$ ddns
```

I recommend copying the `ddns` script to your /usr/local/sbin folder and calling it from a script in one of your cron.\* folders or from a systemd timer.
