# heroku_team_member

[back](../heroku.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    heroku = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_team_member" {
  source = "./modules/heroku/r/heroku_team_member"

  # email - (required) is a type of string
  email = null
  # federated - (optional) is a type of bool
  federated = null
  # role - (required) is a type of string
  role = null
  # team - (required) is a type of string
  team = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required)"
  type        = string
}

variable "federated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "team" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_team_member" "this" {
  email     = var.email
  federated = var.federated
  role      = var.role
  team      = var.team
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_team_member.this.id
}

output "this" {
  value = heroku_team_member.this
}
```

[top](#index)