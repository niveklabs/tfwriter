# azuredevops_project_features

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
module "azuredevops_project_features" {
  source = "./modules/azuredevops/r/azuredevops_project_features"

  # features - (required) is a type of map of string
  features = {}
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "features" {
  description = "(required)"
  type        = map(string)
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_project_features" "this" {
  features   = var.features
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_project_features.this.id
}

output "this" {
  value = azuredevops_project_features.this
}
```

[top](#index)