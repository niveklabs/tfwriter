# azuredevops_group_membership

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
module "azuredevops_group_membership" {
  source = "./modules/azuredevops/r/azuredevops_group_membership"

  # group - (required) is a type of string
  group = null
  # members - (required) is a type of set of string
  members = []
  # mode - (optional) is a type of string
  mode = null
}
```

[top](#index)

### Variables

```terraform
variable "group" {
  description = "(required)"
  type        = string
}

variable "members" {
  description = "(required)"
  type        = set(string)
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_group_membership" "this" {
  # group - (required) is a type of string
  group = var.group
  # members - (required) is a type of set of string
  members = var.members
  # mode - (optional) is a type of string
  mode = var.mode
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_group_membership.this.id
}

output "this" {
  value = azuredevops_group_membership.this
}
```

[top](#index)