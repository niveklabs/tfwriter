# gitlab_project_variable

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
module "gitlab_project_variable" {
  source = "./modules/gitlab/r/gitlab_project_variable"

  # environment_scope - (optional) is a type of string
  environment_scope = null
  # key - (required) is a type of string
  key = null
  # masked - (optional) is a type of bool
  masked = null
  # project - (required) is a type of string
  project = null
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
variable "environment_scope" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "project" {
  description = "(required)"
  type        = string
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
resource "gitlab_project_variable" "this" {
  environment_scope = var.environment_scope
  key               = var.key
  masked            = var.masked
  project           = var.project
  protected         = var.protected
  value             = var.value
  variable_type     = var.variable_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_project_variable.this.id
}

output "this" {
  value = gitlab_project_variable.this
}
```

[top](#index)