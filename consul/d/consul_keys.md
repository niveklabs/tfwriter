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
    consul = ">= 2.10.1"
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
  datacenter = var.datacenter
  namespace  = var.namespace
  token      = var.token

  dynamic "key" {
    for_each = var.key
    content {
      default = key.value["default"]
      name    = key.value["name"]
      path    = key.value["path"]
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