# azuredevops_build_definition_permissions

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_build_definition_permissions" {
  source = "./modules/azuredevops/r/azuredevops_build_definition_permissions"

  # build_definition_id - (required) is a type of string
  build_definition_id = null
  # permissions - (required) is a type of map of string
  permissions = {}
  # principal - (required) is a type of string
  principal = null
  # project_id - (required) is a type of string
  project_id = null
  # replace - (optional) is a type of bool
  replace = null
}
```

[top](#index)

### Variables

```terraform
variable "build_definition_id" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "(required)"
  type        = map(string)
}

variable "principal" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "replace" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_build_definition_permissions" "this" {
  # build_definition_id - (required) is a type of string
  build_definition_id = var.build_definition_id
  # permissions - (required) is a type of map of string
  permissions = var.permissions
  # principal - (required) is a type of string
  principal = var.principal
  # project_id - (required) is a type of string
  project_id = var.project_id
  # replace - (optional) is a type of bool
  replace = var.replace
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_build_definition_permissions.this.id
}

output "this" {
  value = azuredevops_build_definition_permissions.this
}
```

[top](#index)