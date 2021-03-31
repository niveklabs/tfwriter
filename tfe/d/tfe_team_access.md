# tfe_team_access

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/tfe/d/tfe_team_access"

  # team_id - (required) is a type of string
  team_id = null
  # workspace_id - (required) is a type of string
  workspace_id = null
}
```

[top](#index)

### Variables

```terraform
variable "team_id" {
  description = "(required)"
  type        = string
}

variable "workspace_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tfe_team_access" "this" {
  team_id      = var.team_id
  workspace_id = var.workspace_id
}
```

[top](#index)

### Outputs

```terraform
output "access" {
  description = "returns a string"
  value       = data.tfe_team_access.this.access
}

output "id" {
  description = "returns a string"
  value       = data.tfe_team_access.this.id
}

output "permissions" {
  description = "returns a list of object"
  value       = data.tfe_team_access.this.permissions
}

output "this" {
  value = tfe_team_access.this
}
```

[top](#index)