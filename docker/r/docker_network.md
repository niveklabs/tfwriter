# docker_network

[back](../docker.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/docker/r/docker_network"

  # attachable - (optional) is a type of bool
  attachable = null
  # check_duplicate - (optional) is a type of bool
  check_duplicate = null
  # driver - (optional) is a type of string
  driver = null
  # ingress - (optional) is a type of bool
  ingress = null
  # internal - (optional) is a type of bool
  internal = null
  # ipam_driver - (optional) is a type of string
  ipam_driver = null
  # ipv6 - (optional) is a type of bool
  ipv6 = null
  # name - (required) is a type of string
  name = null
  # options - (optional) is a type of map of string
  options = {}

  ipam_config = [{
    aux_address = {}
    gateway     = null
    ip_range    = null
    subnet      = null
  }]

  labels = [{
    label = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "attachable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "check_duplicate" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "driver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ingress" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "internal" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ipam_driver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "options" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ipam_config" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      aux_address = map(string)
      gateway     = string
      ip_range    = string
      subnet      = string
    }
  ))
  default = []
}

variable "labels" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      label = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "docker_network" "this" {
  # attachable - (optional) is a type of bool
  attachable = var.attachable
  # check_duplicate - (optional) is a type of bool
  check_duplicate = var.check_duplicate
  # driver - (optional) is a type of string
  driver = var.driver
  # ingress - (optional) is a type of bool
  ingress = var.ingress
  # internal - (optional) is a type of bool
  internal = var.internal
  # ipam_driver - (optional) is a type of string
  ipam_driver = var.ipam_driver
  # ipv6 - (optional) is a type of bool
  ipv6 = var.ipv6
  # name - (required) is a type of string
  name = var.name
  # options - (optional) is a type of map of string
  options = var.options

  dynamic "ipam_config" {
    for_each = var.ipam_config
    content {
      # aux_address - (optional) is a type of map of string
      aux_address = ipam_config.value["aux_address"]
      # gateway - (optional) is a type of string
      gateway = ipam_config.value["gateway"]
      # ip_range - (optional) is a type of string
      ip_range = ipam_config.value["ip_range"]
      # subnet - (optional) is a type of string
      subnet = ipam_config.value["subnet"]
    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      # label - (required) is a type of string
      label = labels.value["label"]
      # value - (required) is a type of string
      value = labels.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "driver" {
  description = "returns a string"
  value       = docker_network.this.driver
}

output "id" {
  description = "returns a string"
  value       = docker_network.this.id
}

output "internal" {
  description = "returns a bool"
  value       = docker_network.this.internal
}

output "options" {
  description = "returns a map of string"
  value       = docker_network.this.options
}

output "scope" {
  description = "returns a string"
  value       = docker_network.this.scope
}

output "this" {
  value = docker_network.this
}
```

[top](#index)