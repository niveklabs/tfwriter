---
layout: resource
title: ns1
type: provider
resource: ns1
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "ns1" {
  version = "1.9.4"

  # apikey - (optional) is a type of string
  apikey = null
  # enable_ddi - (optional) is a type of bool
  enable_ddi = null
  # endpoint - (optional) is a type of string
  endpoint = null
  # ignore_ssl - (optional) is a type of bool
  ignore_ssl = null
  # rate_limit_parallelism - (optional) is a type of number
  rate_limit_parallelism = null
}
```

[top](#index)

### Resources


- [ns1_apikey](./r/ns1_apikey.md)

- [ns1_datafeed](./r/ns1_datafeed.md)

- [ns1_datasource](./r/ns1_datasource.md)

- [ns1_monitoringjob](./r/ns1_monitoringjob.md)

- [ns1_notifylist](./r/ns1_notifylist.md)

- [ns1_record](./r/ns1_record.md)

- [ns1_team](./r/ns1_team.md)

- [ns1_user](./r/ns1_user.md)

- [ns1_zone](./r/ns1_zone.md)


[top](#index)

### Datasources


- [ns1_dnssec](./d/ns1_dnssec.md)

- [ns1_record](./d/ns1_record.md)

- [ns1_zone](./d/ns1_zone.md)


[top](#index)