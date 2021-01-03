# tfe_team_member

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
    tfe = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_team_member" {
  source = "./modules/tfe/r/tfe_team_member"

  # team_id - (required) is a type of string
  team_id = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "team_id" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_team_member" "this" {
  team_id  = var.team_id
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_team_member.this.id
}

output "this" {
  value = tfe_team_member.this
}
```

[top](#index)