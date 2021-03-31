# kubernetes-alpha

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "kubernetes-alpha" {
  version = "0.3.2"

  # client_certificate - (optional) is a type of string
  client_certificate = null
  # client_key - (optional) is a type of string
  client_key = null
  # cluster_ca_certificate - (optional) is a type of string
  cluster_ca_certificate = null
  # config_context - (optional) is a type of string
  config_context = null
  # config_context_cluster - (optional) is a type of string
  config_context_cluster = null
  # config_context_user - (optional) is a type of string
  config_context_user = null
  # config_path - (optional) is a type of string
  config_path = null
  # exec - (optional) is a type of object
  exec = {
    api_version = null
    args        = []
    command     = null
    env         = {}
  }
  # host - (optional) is a type of string
  host = null
  # insecure - (optional) is a type of bool
  insecure = null
  # password - (optional) is a type of string
  password = null
  # token - (optional) is a type of string
  token = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Resources


- [kubernetes_manifest](./r/kubernetes_manifest.md)


[top](#index)

### Datasources



[top](#index)