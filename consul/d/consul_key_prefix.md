# consul_key_prefix

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/consul/d/consul_key_prefix"

  # datacenter - (optional) is a type of string
  datacenter = null
  # namespace - (optional) is a type of string
  namespace = null
  # path_prefix - (required) is a type of string
  path_prefix = null
  # token - (optional) is a type of string
  token = null

  subkey = [{
    default = null
    name    = null
    path    = null
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

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subkey" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
      name    = string
      path    = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "consul_key_prefix" "this" {
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # path_prefix - (required) is a type of string
  path_prefix = var.path_prefix
  # token - (optional) is a type of string
  token = var.token

  dynamic "subkey" {
    for_each = var.subkey
    content {
      # default - (optional) is a type of string
      default = subkey.value["default"]
      # name - (required) is a type of string
      name = subkey.value["name"]
      # path - (required) is a type of string
      path = subkey.value["path"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = data.consul_key_prefix.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = data.consul_key_prefix.this.id
}

output "subkeys" {
  description = "returns a map of string"
  value       = data.consul_key_prefix.this.subkeys
}

output "var" {
  description = "returns a map of string"
  value       = data.consul_key_prefix.this.var
}

output "this" {
  value = consul_key_prefix.this
}
```

[top](#index)