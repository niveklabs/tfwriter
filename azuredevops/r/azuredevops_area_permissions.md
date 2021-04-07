# azuredevops_area_permissions

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
module "azuredevops_area_permissions" {
  source = "./modules/azuredevops/r/azuredevops_area_permissions"

  # path - (optional) is a type of string
  path = null
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
variable "path" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azuredevops_area_permissions" "this" {
  # path - (optional) is a type of string
  path = var.path
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
  value       = azuredevops_area_permissions.this.id
}

output "this" {
  value = azuredevops_area_permissions.this
}
```

[top](#index)