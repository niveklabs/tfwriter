# consul_namespace

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
module "consul_namespace" {
  source = "./modules/consul/r/consul_namespace"

  # description - (optional) is a type of string
  description = null
  # meta - (optional) is a type of map of string
  meta = {}
  # name - (required) is a type of string
  name = null
  # policy_defaults - (optional) is a type of list of string
  policy_defaults = []
  # role_defaults - (optional) is a type of list of string
  role_defaults = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_defaults" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "role_defaults" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "consul_namespace" "this" {
  description     = var.description
  meta            = var.meta
  name            = var.name
  policy_defaults = var.policy_defaults
  role_defaults   = var.role_defaults
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = consul_namespace.this.id
}

output "this" {
  value = consul_namespace.this
}
```

[top](#index)