# pagerduty_team_membership

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_team_membership" {
  source = "./modules/pagerduty/r/pagerduty_team_membership"

  # role - (optional) is a type of string
  role = null
  # team_id - (required) is a type of string
  team_id = null
  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "team_id" {
  description = "(required)"
  type        = string
}

variable "user_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_team_membership" "this" {
  role    = var.role
  team_id = var.team_id
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = pagerduty_team_membership.this.id
}

output "this" {
  value = pagerduty_team_membership.this
}
```

[top](#index)