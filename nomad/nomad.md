---
layout: resource
title: nomad
type: provider
resource: nomad
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "nomad" {
  version = "1.4.14"

  # address - (required) is a type of string
  address = null
  # ca_file - (optional) is a type of string
  ca_file = null
  # ca_pem - (optional) is a type of string
  ca_pem = null
  # cert_file - (optional) is a type of string
  cert_file = null
  # cert_pem - (optional) is a type of string
  cert_pem = null
  # consul_token - (optional) is a type of string
  consul_token = null
  # http_auth - (optional) is a type of string
  http_auth = null
  # key_file - (optional) is a type of string
  key_file = null
  # key_pem - (optional) is a type of string
  key_pem = null
  # region - (optional) is a type of string
  region = null
  # secret_id - (optional) is a type of string
  secret_id = null
  # vault_token - (optional) is a type of string
  vault_token = null

  # NestingList
  headers {
    # name - (required) is a type of string
    name = null
    # value - (required) is a type of string
    value = null
  }
}
```

[top](#index)

### Resources


- [nomad_acl_policy](./r/nomad_acl_policy.md)

- [nomad_acl_token](./r/nomad_acl_token.md)

- [nomad_job](./r/nomad_job.md)

- [nomad_namespace](./r/nomad_namespace.md)

- [nomad_quota_specification](./r/nomad_quota_specification.md)

- [nomad_scheduler_config](./r/nomad_scheduler_config.md)

- [nomad_sentinel_policy](./r/nomad_sentinel_policy.md)

- [nomad_volume](./r/nomad_volume.md)


[top](#index)

### Datasources


- [nomad_acl_policies](./d/nomad_acl_policies.md)

- [nomad_acl_policy](./d/nomad_acl_policy.md)

- [nomad_acl_token](./d/nomad_acl_token.md)

- [nomad_acl_tokens](./d/nomad_acl_tokens.md)

- [nomad_datacenters](./d/nomad_datacenters.md)

- [nomad_deployments](./d/nomad_deployments.md)

- [nomad_job](./d/nomad_job.md)

- [nomad_job_parser](./d/nomad_job_parser.md)

- [nomad_namespace](./d/nomad_namespace.md)

- [nomad_namespaces](./d/nomad_namespaces.md)

- [nomad_plugin](./d/nomad_plugin.md)

- [nomad_plugins](./d/nomad_plugins.md)

- [nomad_regions](./d/nomad_regions.md)

- [nomad_scaling_policies](./d/nomad_scaling_policies.md)

- [nomad_scaling_policy](./d/nomad_scaling_policy.md)

- [nomad_scheduler_config](./d/nomad_scheduler_config.md)

- [nomad_volumes](./d/nomad_volumes.md)


[top](#index)