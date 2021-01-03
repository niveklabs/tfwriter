# tfe_organization

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
module "tfe_organization" {
  source = "./modules/tfe/r/tfe_organization"

  # collaborator_auth_policy - (optional) is a type of string
  collaborator_auth_policy = null
  # cost_estimation_enabled - (optional) is a type of bool
  cost_estimation_enabled = null
  # email - (required) is a type of string
  email = null
  # name - (required) is a type of string
  name = null
  # owners_team_saml_role_id - (optional) is a type of string
  owners_team_saml_role_id = null
  # session_remember_minutes - (optional) is a type of number
  session_remember_minutes = null
  # session_timeout_minutes - (optional) is a type of number
  session_timeout_minutes = null
}
```

[top](#index)

### Variables

```terraform
variable "collaborator_auth_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cost_estimation_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "owners_team_saml_role_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_remember_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_timeout_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tfe_organization" "this" {
  collaborator_auth_policy = var.collaborator_auth_policy
  cost_estimation_enabled  = var.cost_estimation_enabled
  email                    = var.email
  name                     = var.name
  owners_team_saml_role_id = var.owners_team_saml_role_id
  session_remember_minutes = var.session_remember_minutes
  session_timeout_minutes  = var.session_timeout_minutes
}
```

[top](#index)

### Outputs

```terraform
output "cost_estimation_enabled" {
  description = "returns a bool"
  value       = tfe_organization.this.cost_estimation_enabled
}

output "id" {
  description = "returns a string"
  value       = tfe_organization.this.id
}

output "this" {
  value = tfe_organization.this
}
```

[top](#index)