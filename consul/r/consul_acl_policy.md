# consul_acl_policy

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
module "consul_acl_policy" {
  source = "./modules/consul/r/consul_acl_policy"

  # datacenters - (optional) is a type of set of string
  datacenters = []
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # rules - (required) is a type of string
  rules = null
}
```

[top](#index)

### Variables

```terraform
variable "datacenters" {
  description = "(optional) - The ACL policy datacenters."
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional) - The ACL policy description."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The ACL policy name."
  type        = string
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rules" {
  description = "(required) - The ACL policy rules."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "consul_acl_policy" "this" {
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
  value       = consul_acl_policy.this.id
}

output "this" {
  value = consul_acl_policy.this
}
```

[top](#index)