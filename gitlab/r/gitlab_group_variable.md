# gitlab_group_variable

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
    gitlab = ">= 3.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_group_variable" {
  source = "./modules/gitlab/r/gitlab_group_variable"

  # group - (required) is a type of string
  group = null
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
variable "group" {
  description = "(required)"
  type        = string
}

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
resource "gitlab_group_variable" "this" {
  group         = var.group
  key           = var.key
  masked        = var.masked
  protected     = var.protected
  value         = var.value
  variable_type = var.variable_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_group_variable.this.id
}

output "this" {
  value = gitlab_group_variable.this
}
```

[top](#index)