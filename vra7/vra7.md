---
layout: resource
title: vra7
type: provider
resource: vra7
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "vra7" {
  version = "3.0.2"

  # host - (required) is a type of string
  host = null
  # insecure - (optional) is a type of bool
  insecure = null
  # password - (required) is a type of string
  password = null
  # tenant - (required) is a type of string
  tenant = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Resources


- [vra7_deployment](./r/vra7_deployment.md)


[top](#index)

### Datasources


- [vra7_deployment](./d/vra7_deployment.md)


[top](#index)