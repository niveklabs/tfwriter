# tfe_team_members

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
module "tfe_team_members" {
  source = "./modules/tfe/r/tfe_team_members"

  # team_id - (required) is a type of string
  team_id = null
  # usernames - (required) is a type of set of string
  usernames = []
}
```

[top](#index)

### Variables

```terraform
variable "team_id" {
  description = "(required)"
  type        = string
}

variable "usernames" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "tfe_team_members" "this" {
  # team_id - (required) is a type of string
  team_id = var.team_id
  # usernames - (required) is a type of set of string
  usernames = var.usernames
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_team_members.this.id
}

output "this" {
  value = tfe_team_members.this
}
```

[top](#index)