---
layout: resource
title: skytap
type: provider
resource: skytap
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "skytap" {
  version = "0.14.4"

  # api_token - (required) is a type of string
  api_token = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Resources


- [skytap_environment](./r/skytap_environment.md)

- [skytap_icnr_tunnel](./r/skytap_icnr_tunnel.md)

- [skytap_label_category](./r/skytap_label_category.md)

- [skytap_network](./r/skytap_network.md)

- [skytap_project](./r/skytap_project.md)

- [skytap_vm](./r/skytap_vm.md)


[top](#index)

### Datasources


- [skytap_project](./d/skytap_project.md)

- [skytap_template](./d/skytap_template.md)


[top](#index)