# docker_network

[back](../docker.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    docker = ">= 2.7.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "docker_network" {
  source = "./modules/docker/d/docker_network"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "docker_network" "this" {
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "driver" {
  description = "returns a string"
  value       = data.docker_network.this.driver
}

output "id" {
  description = "returns a string"
  value       = data.docker_network.this.id
}

output "internal" {
  description = "returns a bool"
  value       = data.docker_network.this.internal
}

output "ipam_config" {
  description = "returns a set of object"
  value       = data.docker_network.this.ipam_config
}

output "options" {
  description = "returns a map of string"
  value       = data.docker_network.this.options
}

output "scope" {
  description = "returns a string"
  value       = data.docker_network.this.scope
}

output "this" {
  value = docker_network.this
}
```

[top](#index)