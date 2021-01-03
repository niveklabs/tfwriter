# helm

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "helm" {
  version = "2.0.1"

  # debug - (optional) is a type of bool
  debug = null
  # helm_driver - (optional) is a type of string
  helm_driver = null
  # plugins_path - (optional) is a type of string
  plugins_path = null
  # registry_config_path - (optional) is a type of string
  registry_config_path = null
  # repository_cache - (optional) is a type of string
  repository_cache = null
  # repository_config_path - (optional) is a type of string
  repository_config_path = null

  # NestingList
  kubernetes {
    # client_certificate - (optional) is a type of string
    client_certificate = null
    # client_key - (optional) is a type of string
    client_key = null
    # cluster_ca_certificate - (optional) is a type of string
    cluster_ca_certificate = null
    # config_context - (optional) is a type of string
    config_context = null
    # config_context_auth_info - (optional) is a type of string
    config_context_auth_info = null
    # config_context_cluster - (optional) is a type of string
    config_context_cluster = null
    # config_path - (optional) is a type of string
    config_path = null
    # config_paths - (optional) is a type of list of string
    config_paths = []
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

    # NestingList
    exec {
      # api_version - (required) is a type of string
      api_version = null
      # args - (optional) is a type of list of string
      args = []
      # command - (required) is a type of string
      command = null
      # env - (optional) is a type of map of string
      env = {}
    }
  }
}
```

[top](#index)

### Resources


- [helm_release](./r/helm_release.md)


[top](#index)

### Datasources



[top](#index)