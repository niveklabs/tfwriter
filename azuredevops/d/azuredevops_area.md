# azuredevops_area

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azuredevops_area" {
  source = "./modules/azuredevops/d/azuredevops_area"

  # fetch_children - (optional) is a type of bool
  fetch_children = null
  # path - (optional) is a type of string
  path = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "fetch_children" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azuredevops_area" "this" {
  # fetch_children - (optional) is a type of bool
  fetch_children = var.fetch_children
  # path - (optional) is a type of string
  path = var.path
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "children" {
  description = "returns a list of object"
  value       = data.azuredevops_area.this.children
}

output "has_children" {
  description = "returns a bool"
  value       = data.azuredevops_area.this.has_children
}

output "id" {
  description = "returns a string"
  value       = data.azuredevops_area.this.id
}

output "name" {
  description = "returns a string"
  value       = data.azuredevops_area.this.name
}

output "path" {
  description = "returns a string"
  value       = data.azuredevops_area.this.path
}

output "this" {
  value = azuredevops_area.this
}
```

[top](#index)