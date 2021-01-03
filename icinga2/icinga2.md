# icinga2

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "icinga2" {
  version = "0.4.0"

  # api_password - (required) is a type of string
  api_password = null
  # api_url - (required) is a type of string
  api_url = null
  # api_user - (required) is a type of string
  api_user = null
  # insecure_skip_tls_verify - (optional) is a type of bool
  insecure_skip_tls_verify = null
}
```

[top](#index)

### Resources


- [icinga2_checkcommand](./r/icinga2_checkcommand.md)

- [icinga2_host](./r/icinga2_host.md)

- [icinga2_hostgroup](./r/icinga2_hostgroup.md)

- [icinga2_notification](./r/icinga2_notification.md)

- [icinga2_service](./r/icinga2_service.md)

- [icinga2_user](./r/icinga2_user.md)


[top](#index)

### Datasources



[top](#index)