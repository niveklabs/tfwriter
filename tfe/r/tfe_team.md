# tfe_team

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tfe = ">= 0.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_team" {
  source = "./modules/tfe/r/tfe_team"

  # name - (required) is a type of string
  name = null
  # organization - (required) is a type of string
  organization = null
  # visibility - (optional) is a type of string
  visibility = null

  organization_access = [{
    manage_policies     = null
    manage_vcs_settings = null
    manage_workspaces   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "organization" {
  description = "(required)"
  type        = string
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "organization_access" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      manage_policies     = bool
      manage_vcs_settings = bool
      manage_workspaces   = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tfe_team" "this" {
  # name - (required) is a type of string
  name = var.name
  # organization - (required) is a type of string
  organization = var.organization
  # visibility - (optional) is a type of string
  visibility = var.visibility

  dynamic "organization_access" {
    for_each = var.organization_access
    content {
      # manage_policies - (optional) is a type of bool
      manage_policies = organization_access.value["manage_policies"]
      # manage_vcs_settings - (optional) is a type of bool
      manage_vcs_settings = organization_access.value["manage_vcs_settings"]
      # manage_workspaces - (optional) is a type of bool
      manage_workspaces = organization_access.value["manage_workspaces"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_team.this.id
}

output "this" {
  value = tfe_team.this
}
```

[top](#index)