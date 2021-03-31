# ad

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "ad" {
  version = "0.4.1"

  # krb_conf - (optional) is a type of string
  krb_conf = null
  # krb_realm - (optional) is a type of string
  krb_realm = null
  # krb_spn - (optional) is a type of string
  krb_spn = null
  # winrm_hostname - (required) is a type of string
  winrm_hostname = null
  # winrm_insecure - (optional) is a type of bool
  winrm_insecure = null
  # winrm_password - (required) is a type of string
  winrm_password = null
  # winrm_port - (optional) is a type of number
  winrm_port = null
  # winrm_proto - (optional) is a type of string
  winrm_proto = null
  # winrm_use_ntlm - (optional) is a type of bool
  winrm_use_ntlm = null
  # winrm_username - (required) is a type of string
  winrm_username = null
}
```

[top](#index)

### Resources


- [ad_computer](./r/ad_computer.md)

- [ad_gplink](./r/ad_gplink.md)

- [ad_gpo](./r/ad_gpo.md)

- [ad_gpo_security](./r/ad_gpo_security.md)

- [ad_group](./r/ad_group.md)

- [ad_group_membership](./r/ad_group_membership.md)

- [ad_ou](./r/ad_ou.md)

- [ad_user](./r/ad_user.md)


[top](#index)

### Datasources


- [ad_computer](./d/ad_computer.md)

- [ad_gpo](./d/ad_gpo.md)

- [ad_group](./d/ad_group.md)

- [ad_ou](./d/ad_ou.md)

- [ad_user](./d/ad_user.md)


[top](#index)