# opsgenie_user

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_user" {
  source = "./modules/opsgenie/d/opsgenie_user"

  # full_name - (optional) is a type of string
  full_name = null
  # locale - (optional) is a type of string
  locale = null
  # role - (optional) is a type of string
  role = null
  # timezone - (optional) is a type of string
  timezone = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "full_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "locale" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "opsgenie_user" "this" {
  full_name = var.full_name
  locale    = var.locale
  role      = var.role
  timezone  = var.timezone
  username  = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.opsgenie_user.this.id
}

output "this" {
  value = opsgenie_user.this
}
```

[top](#index)