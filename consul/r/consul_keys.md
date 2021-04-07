# consul_keys

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
module "consul_keys" {
  source = "./modules/consul/r/consul_keys"

  # datacenter - (optional) is a type of string
  datacenter = null
  # namespace - (optional) is a type of string
  namespace = null
  # token - (optional) is a type of string
  token = null

  key = [{
    default = null
    delete  = null
    flags   = null
    name    = null
    path    = null
    value   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
      delete  = bool
      flags   = number
      name    = string
      path    = string
      value   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "consul_keys" "this" {
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # token - (optional) is a type of string
  token = var.token

  dynamic "key" {
    for_each = var.key
    content {
      # default - (optional) is a type of string
      default = key.value["default"]
      # delete - (optional) is a type of bool
      delete = key.value["delete"]
      # flags - (optional) is a type of number
      flags = key.value["flags"]
      # name - (optional) is a type of string
      name = key.value["name"]
      # path - (required) is a type of string
      path = key.value["path"]
      # value - (optional) is a type of string
      value = key.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = consul_keys.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = consul_keys.this.id
}

output "var" {
  description = "returns a map of string"
  value       = consul_keys.this.var
}

output "this" {
  value = consul_keys.this
}
```

[top](#index)