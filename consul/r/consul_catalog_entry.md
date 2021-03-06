# consul_catalog_entry

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_catalog_entry" {
  source = "./modules/consul/r/consul_catalog_entry"

  # address - (required) is a type of string
  address = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # node - (required) is a type of string
  node = null
  # token - (optional) is a type of string
  token = null

  service = [{
    address = null
    id      = null
    name    = null
    port    = null
    tags    = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required)"
  type        = string
}

variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node" {
  description = "(required)"
  type        = string
}

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address = string
      id      = string
      name    = string
      port    = number
      tags    = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "consul_catalog_entry" "this" {
  # address - (required) is a type of string
  address = var.address
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # node - (required) is a type of string
  node = var.node
  # token - (optional) is a type of string
  token = var.token

  dynamic "service" {
    for_each = var.service
    content {
      # address - (optional) is a type of string
      address = service.value["address"]
      # id - (optional) is a type of string
      id = service.value["id"]
      # name - (required) is a type of string
      name = service.value["name"]
      # port - (optional) is a type of number
      port = service.value["port"]
      # tags - (optional) is a type of set of string
      tags = service.value["tags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = consul_catalog_entry.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = consul_catalog_entry.this.id
}

output "this" {
  value = consul_catalog_entry.this
}
```

[top](#index)