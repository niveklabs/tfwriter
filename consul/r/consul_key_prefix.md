# consul_key_prefix

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
module "consul_key_prefix" {
  source = "./modules/consul/r/consul_key_prefix"

  # datacenter - (optional) is a type of string
  datacenter = null
  # namespace - (optional) is a type of string
  namespace = null
  # path_prefix - (required) is a type of string
  path_prefix = null
  # subkeys - (optional) is a type of map of string
  subkeys = {}
  # token - (optional) is a type of string
  token = null

  subkey = [{
    flags = null
    path  = null
    value = null
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

variable "path_prefix" {
  description = "(required)"
  type        = string
}

variable "subkeys" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subkey" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      flags = number
      path  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "consul_key_prefix" "this" {
  datacenter  = var.datacenter
  namespace   = var.namespace
  path_prefix = var.path_prefix
  subkeys     = var.subkeys
  token       = var.token

  dynamic "subkey" {
    for_each = var.subkey
    content {
      flags = subkey.value["flags"]
      path  = subkey.value["path"]
      value = subkey.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = consul_key_prefix.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = consul_key_prefix.this.id
}

output "this" {
  value = consul_key_prefix.this
}
```

[top](#index)