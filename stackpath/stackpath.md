---
layout: resource
title: stackpath
type: provider
resource: stackpath
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "stackpath" {
  version = "1.3.3"

  # access_token - (optional) is a type of string
  access_token = null
  # base_url - (optional) is a type of string
  base_url = null
  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # stack_id - (optional) is a type of string
  stack_id = null
}
```

[top](#index)

### Resources


- [stackpath_compute_network_policy](./r/stackpath_compute_network_policy.md)

- [stackpath_compute_workload](./r/stackpath_compute_workload.md)

- [stackpath_object_storage_bucket](./r/stackpath_object_storage_bucket.md)


[top](#index)

### Datasources



[top](#index)