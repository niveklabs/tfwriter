# consul_keys

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
module "consul_keys" {
  source = "./modules/consul/d/consul_keys"

  # datacenter - (optional) is a type of string
  datacenter = null
  # namespace - (optional) is a type of string
  namespace = null
  # token - (optional) is a type of string
  token = null

  key = [{
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
data "consul_keys" "this" {
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
      # name - (required) is a type of string
      name = key.value["name"]
      # path - (required) is a type of string
      path = key.value["path"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = data.consul_keys.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = data.consul_keys.this.id
}

output "var" {
  description = "returns a map of string"
  value       = data.consul_keys.this.var
}

output "this" {
  value = consul_keys.this
}
```

[top](#index)