# azuredevops_resource_authorization

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
module "azuredevops_resource_authorization" {
  source = "./modules/azuredevops/r/azuredevops_resource_authorization"

  # authorized - (required) is a type of bool
  authorized = null
  # definition_id - (optional) is a type of number
  definition_id = null
  # project_id - (required) is a type of string
  project_id = null
  # resource_id - (required) is a type of string
  resource_id = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "authorized" {
  description = "(required) - indicates whether the resource is authorized for use"
  type        = bool
}

variable "definition_id" {
  description = "(optional) - id of the build definition"
  type        = number
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required) - id of the resource"
  type        = string
}

variable "type" {
  description = "(optional) - type of the resource"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_resource_authorization" "this" {
  # authorized - (required) is a type of bool
  authorized = var.authorized
  # definition_id - (optional) is a type of number
  definition_id = var.definition_id
  # project_id - (required) is a type of string
  project_id = var.project_id
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_resource_authorization.this.id
}

output "this" {
  value = azuredevops_resource_authorization.this
}
```

[top](#index)