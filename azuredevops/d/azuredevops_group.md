# azuredevops_group

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
module "azuredevops_group" {
  source = "./modules/azuredevops/d/azuredevops_group"

  # name - (required) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
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
data "azuredevops_group" "this" {
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "descriptor" {
  description = "returns a string"
  value       = data.azuredevops_group.this.descriptor
}

output "id" {
  description = "returns a string"
  value       = data.azuredevops_group.this.id
}

output "origin" {
  description = "returns a string"
  value       = data.azuredevops_group.this.origin
}

output "origin_id" {
  description = "returns a string"
  value       = data.azuredevops_group.this.origin_id
}

output "this" {
  value = azuredevops_group.this
}
```

[top](#index)