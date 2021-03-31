# tfe_team_token

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
module "tfe_team_token" {
  source = "./modules/tfe/r/tfe_team_token"

  # force_regenerate - (optional) is a type of bool
  force_regenerate = null
  # team_id - (required) is a type of string
  team_id = null
}
```

[top](#index)

### Variables

```terraform
variable "force_regenerate" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "team_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_team_token" "this" {
  force_regenerate = var.force_regenerate
  team_id          = var.team_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_team_token.this.id
}

output "token" {
  description = "returns a string"
  value       = tfe_team_token.this.token
  sensitive   = true
}

output "this" {
  value = tfe_team_token.this
}
```

[top](#index)