---
layout: resource
title: sdm
type: provider
resource: sdm
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "sdm" {
  version = "1.0.19"

  # api_access_key - (optional) is a type of string
  api_access_key = null
  # api_secret_key - (optional) is a type of string
  api_secret_key = null
  # host - (optional) is a type of string
  host = null
}
```

[top](#index)

### Resources


- [sdm_account](./r/sdm_account.md)

- [sdm_account_attachment](./r/sdm_account_attachment.md)

- [sdm_account_grant](./r/sdm_account_grant.md)

- [sdm_node](./r/sdm_node.md)

- [sdm_resource](./r/sdm_resource.md)

- [sdm_role](./r/sdm_role.md)

- [sdm_role_attachment](./r/sdm_role_attachment.md)

- [sdm_role_grant](./r/sdm_role_grant.md)

- [sdm_secret_store](./r/sdm_secret_store.md)


[top](#index)

### Datasources


- [sdm_account](./d/sdm_account.md)

- [sdm_account_attachment](./d/sdm_account_attachment.md)

- [sdm_account_grant](./d/sdm_account_grant.md)

- [sdm_node](./d/sdm_node.md)

- [sdm_resource](./d/sdm_resource.md)

- [sdm_role](./d/sdm_role.md)

- [sdm_role_attachment](./d/sdm_role_attachment.md)

- [sdm_role_grant](./d/sdm_role_grant.md)

- [sdm_secret_store](./d/sdm_secret_store.md)

- [sdm_ssh_ca_pubkey](./d/sdm_ssh_ca_pubkey.md)


[top](#index)