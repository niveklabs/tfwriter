# azuredevops_projects

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
module "azuredevops_projects" {
  source = "./modules/azuredevops/d/azuredevops_projects"

  # name - (optional) is a type of string
  name = null
  # state - (optional) is a type of string
  state = null
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

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuredevops_projects" "this" {
  name  = var.name
  state = var.state
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azuredevops_projects.this.id
}

output "projects" {
  description = "returns a set of object"
  value       = data.azuredevops_projects.this.projects
}

output "this" {
  value = azuredevops_projects.this
}
```

[top](#index)