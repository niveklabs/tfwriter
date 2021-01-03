# consul_acl_policy

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
module "consul_acl_policy" {
  source = "./modules/consul/d/consul_acl_policy"

  # datacenters - (optional) is a type of list of string
  datacenters = []
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # rules - (optional) is a type of string
  rules = null
}
```

[top](#index)

### Variables

```terraform
variable "datacenters" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rules" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "consul_acl_policy" "this" {
  datacenters = var.datacenters
  description = var.description
  name        = var.name
  namespace   = var.namespace
  rules       = var.rules
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.consul_acl_policy.this.id
}

output "this" {
  value = consul_acl_policy.this
}
```

[top](#index)