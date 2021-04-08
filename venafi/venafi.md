---
layout: resource
title: venafi
type: provider
resource: venafi
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "venafi" {
  version = "0.11.2"

  # access_token - (optional) is a type of string
  access_token = null
  # api_key - (optional) is a type of string
  api_key = null
  # dev_mode - (optional) is a type of bool
  dev_mode = null
  # tpp_password - (optional) is a type of string
  tpp_password = null
  # tpp_username - (optional) is a type of string
  tpp_username = null
  # trust_bundle - (optional) is a type of string
  trust_bundle = null
  # url - (optional) is a type of string
  url = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Resources


- [venafi_certificate](./r/venafi_certificate.md)


[top](#index)

### Datasources



[top](#index)