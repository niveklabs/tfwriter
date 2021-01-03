# docker

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "docker" {
  version = "2.7.2"

  # ca_material - (optional) is a type of string
  ca_material = null
  # cert_material - (optional) is a type of string
  cert_material = null
  # cert_path - (optional) is a type of string
  cert_path = null
  # host - (optional) is a type of string
  host = null
  # key_material - (optional) is a type of string
  key_material = null

  # NestingSet
  registry_auth {
    # address - (required) is a type of string
    address = null
    # config_file - (optional) is a type of string
    config_file = null
    # config_file_content - (optional) is a type of string
    config_file_content = null
    # password - (optional) is a type of string
    password = null
    # username - (optional) is a type of string
    username = null
  }
}
```

[top](#index)

### Resources


- [docker_config](./r/docker_config.md)

- [docker_container](./r/docker_container.md)

- [docker_image](./r/docker_image.md)

- [docker_network](./r/docker_network.md)

- [docker_secret](./r/docker_secret.md)

- [docker_service](./r/docker_service.md)

- [docker_volume](./r/docker_volume.md)


[top](#index)

### Datasources


- [docker_network](./d/docker_network.md)

- [docker_registry_image](./d/docker_registry_image.md)


[top](#index)