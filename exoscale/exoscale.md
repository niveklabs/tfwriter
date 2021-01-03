# exoscale

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "exoscale" {
  version = "0.21.0"

  # compute_endpoint - (optional) is a type of string
  compute_endpoint = null
  # config - (optional) is a type of string
  config = null
  # delay - (optional) is a type of number
  delay = null
  # dns_endpoint - (optional) is a type of string
  dns_endpoint = null
  # environment - (optional) is a type of string
  environment = null
  # gzip_user_data - (optional) is a type of bool
  gzip_user_data = null
  # key - (optional) is a type of string
  key = null
  # profile - (optional) is a type of string
  profile = null
  # region - (optional) is a type of string
  region = null
  # secret - (optional) is a type of string
  secret = null
  # timeout - (optional) is a type of number
  timeout = null
  # token - (optional) is a type of string
  token = null
}
```

[top](#index)

### Resources


- [exoscale_affinity](./r/exoscale_affinity.md)

- [exoscale_compute](./r/exoscale_compute.md)

- [exoscale_domain](./r/exoscale_domain.md)

- [exoscale_domain_record](./r/exoscale_domain_record.md)

- [exoscale_instance_pool](./r/exoscale_instance_pool.md)

- [exoscale_ipaddress](./r/exoscale_ipaddress.md)

- [exoscale_network](./r/exoscale_network.md)

- [exoscale_nic](./r/exoscale_nic.md)

- [exoscale_nlb](./r/exoscale_nlb.md)

- [exoscale_nlb_service](./r/exoscale_nlb_service.md)

- [exoscale_secondary_ipaddress](./r/exoscale_secondary_ipaddress.md)

- [exoscale_security_group](./r/exoscale_security_group.md)

- [exoscale_security_group_rule](./r/exoscale_security_group_rule.md)

- [exoscale_security_group_rules](./r/exoscale_security_group_rules.md)

- [exoscale_ssh_keypair](./r/exoscale_ssh_keypair.md)


[top](#index)

### Datasources


- [exoscale_affinity](./d/exoscale_affinity.md)

- [exoscale_compute](./d/exoscale_compute.md)

- [exoscale_compute_ipaddress](./d/exoscale_compute_ipaddress.md)

- [exoscale_compute_template](./d/exoscale_compute_template.md)

- [exoscale_domain](./d/exoscale_domain.md)

- [exoscale_domain_record](./d/exoscale_domain_record.md)

- [exoscale_network](./d/exoscale_network.md)

- [exoscale_nlb](./d/exoscale_nlb.md)

- [exoscale_security_group](./d/exoscale_security_group.md)


[top](#index)