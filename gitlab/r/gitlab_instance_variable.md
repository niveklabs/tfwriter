# gitlab_instance_variable

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gitlab = ">= 3.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_instance_variable" {
  source = "./modules/gitlab/r/gitlab_instance_variable"

  # key - (required) is a type of string
  key = null
  # masked - (optional) is a type of bool
  masked = null
  # protected - (optional) is a type of bool
  protected = null
  # value - (required) is a type of string
  value = null
  # variable_type - (optional) is a type of string
  variable_type = null
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required)"
  type        = string
}

variable "masked" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "protected" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "value" {
  description = "(required)"
  type        = string
}

variable "variable_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_instance_variable" "this" {
  # key - (required) is a type of string
  key = var.key
  # masked - (optional) is a type of bool
  masked = var.masked
  # protected - (optional) is a type of bool
  protected = var.protected
  # value - (required) is a type of string
  value = var.value
  # variable_type - (optional) is a type of string
  variable_type = var.variable_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_instance_variable.this.id
}

output "this" {
  value = gitlab_instance_variable.this
}
```

[top](#index)