# launchdarkly_team_member

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_team_member" {
  source = "./modules/launchdarkly/r/launchdarkly_team_member"

  # custom_roles - (optional) is a type of set of string
  custom_roles = []
  # email - (required) is a type of string
  email = null
  # first_name - (optional) is a type of string
  first_name = null
  # last_name - (optional) is a type of string
  last_name = null
  # role - (optional) is a type of string
  role = null
}
```

[top](#index)

### Variables

```terraform
variable "custom_roles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "first_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "launchdarkly_team_member" "this" {
  custom_roles = var.custom_roles
  email        = var.email
  first_name   = var.first_name
  last_name    = var.last_name
  role         = var.role
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = launchdarkly_team_member.this.id
}

output "role" {
  description = "returns a string"
  value       = launchdarkly_team_member.this.role
}

output "this" {
  value = launchdarkly_team_member.this
}
```

[top](#index)