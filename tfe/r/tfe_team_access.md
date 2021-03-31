# tfe_team_access

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
module "tfe_team_access" {
  source = "./modules/tfe/r/tfe_team_access"

  # access - (optional) is a type of string
  access = null
  # team_id - (required) is a type of string
  team_id = null
  # workspace_id - (required) is a type of string
  workspace_id = null

  permissions = [{
    runs              = null
    sentinel_mocks    = null
    state_versions    = null
    variables         = null
    workspace_locking = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "team_id" {
  description = "(required)"
  type        = string
}

variable "workspace_id" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      runs              = string
      sentinel_mocks    = string
      state_versions    = string
      variables         = string
      workspace_locking = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tfe_team_access" "this" {
  access       = var.access
  team_id      = var.team_id
  workspace_id = var.workspace_id

  dynamic "permissions" {
    for_each = var.permissions
    content {
      runs              = permissions.value["runs"]
      sentinel_mocks    = permissions.value["sentinel_mocks"]
      state_versions    = permissions.value["state_versions"]
      variables         = permissions.value["variables"]
      workspace_locking = permissions.value["workspace_locking"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access" {
  description = "returns a string"
  value       = tfe_team_access.this.access
}

output "id" {
  description = "returns a string"
  value       = tfe_team_access.this.id
}

output "this" {
  value = tfe_team_access.this
}
```

[top](#index)