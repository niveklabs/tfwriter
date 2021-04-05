# okta_admin_role_targets

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_admin_role_targets" {
  source = "./modules/okta/r/okta_admin_role_targets"

  # apps - (optional) is a type of set of string
  apps = []
  # groups - (optional) is a type of set of string
  groups = []
  # role_type - (required) is a type of string
  role_type = null
  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "apps" {
  description = "(optional) - List of app names (name represents set of app instances) or a combination of app name and app instance ID (like 'salesforce' or 'facebook.0oapsqQ6dv19pqyEo0g3')"
  type        = set(string)
  default     = null
}

variable "groups" {
  description = "(optional) - List of group IDs"
  type        = set(string)
  default     = null
}

variable "role_type" {
  description = "(required) - Type of the role that is assigned to the user and supports optional targets"
  type        = string
}

variable "user_id" {
  description = "(required) - User associated with the role"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "okta_admin_role_targets" "this" {
  apps      = var.apps
  groups    = var.groups
  role_type = var.role_type
  user_id   = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_admin_role_targets.this.id
}

output "role_id" {
  description = "returns a string"
  value       = okta_admin_role_targets.this.role_id
}

output "this" {
  value = okta_admin_role_targets.this
}
```

[top](#index)