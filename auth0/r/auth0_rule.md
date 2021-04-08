# auth0_rule

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_rule" {
  source = "./modules/auth0/r/auth0_rule"

  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # order - (optional) is a type of number
  order = null
  # script - (required) is a type of string
  script = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "order" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "script" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "auth0_rule" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # order - (optional) is a type of number
  order = var.order
  # script - (required) is a type of string
  script = var.script
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_rule.this.id
}

output "order" {
  description = "returns a number"
  value       = auth0_rule.this.order
}

output "this" {
  value = auth0_rule.this
}
```

[top](#index)