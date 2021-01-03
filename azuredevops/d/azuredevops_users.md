# azuredevops_users

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
module "azuredevops_users" {
  source = "./modules/azuredevops/d/azuredevops_users"

  # origin - (optional) is a type of string
  origin = null
  # origin_id - (optional) is a type of string
  origin_id = null
  # principal_name - (optional) is a type of string
  principal_name = null
  # subject_types - (optional) is a type of set of string
  subject_types = []
}
```

[top](#index)

### Variables

```terraform
variable "origin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "origin_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "principal_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subject_types" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuredevops_users" "this" {
  origin         = var.origin
  origin_id      = var.origin_id
  principal_name = var.principal_name
  subject_types  = var.subject_types
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azuredevops_users.this.id
}

output "users" {
  description = "returns a set of object"
  value       = data.azuredevops_users.this.users
}

output "this" {
  value = azuredevops_users.this
}
```

[top](#index)