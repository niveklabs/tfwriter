# tfe_team_organization_member

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
module "tfe_team_organization_member" {
  source = "./modules/tfe/r/tfe_team_organization_member"

  # organization_membership_id - (required) is a type of string
  organization_membership_id = null
  # team_id - (required) is a type of string
  team_id = null
}
```

[top](#index)

### Variables

```terraform
variable "organization_membership_id" {
  description = "(required)"
  type        = string
}

variable "team_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_team_organization_member" "this" {
  organization_membership_id = var.organization_membership_id
  team_id                    = var.team_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_team_organization_member.this.id
}

output "this" {
  value = tfe_team_organization_member.this
}
```

[top](#index)