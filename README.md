DNSimple Dynamic DNS
==================

DNSimple Dynamic DNS is a script to update the IPv4 and IPv6 addresses for a particular record in DNSimple using either the public IP addresses or interface IP addresses for a computer.


Usage
-----

Edit the `ddns` script to fill in the parameters.

The `token` parameter is your API token obtained from "Account" -> "API tokens" in the DNSimple interface. The `zone` parameter is the DNS zone, such as 'example.com'. The `arecord` and `aaaarecord` parameters are the DNSimple id of the record to update. The `ifip` parameter indicates whether the script should get the IP addresses from the primary internet interface or from an external service (icanhazip.com). You probably want `ifip=false` unless you know what you are doing.

I recommend copying the `ddns` script to your cron.hourly folder (with root only read permission) so that your DNS record gets automatically updated.
