# azuredevops_project

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
    azuredevops = ">= 0.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_project" {
  source = "./modules/azuredevops/d/azuredevops_project"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuredevops_project" "this" {
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.azuredevops_project.this.description
}

output "features" {
  description = "returns a map of string"
  value       = data.azuredevops_project.this.features
}

output "id" {
  description = "returns a string"
  value       = data.azuredevops_project.this.id
}

output "process_template_id" {
  description = "returns a string"
  value       = data.azuredevops_project.this.process_template_id
}

output "version_control" {
  description = "returns a string"
  value       = data.azuredevops_project.this.version_control
}

output "visibility" {
  description = "returns a string"
  value       = data.azuredevops_project.this.visibility
}

output "work_item_template" {
  description = "returns a string"
  value       = data.azuredevops_project.this.work_item_template
}

output "this" {
  value = azuredevops_project.this
}
```

[top](#index)