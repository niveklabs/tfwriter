# azuread_users

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuread = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_users" {
  source = "./modules/azuread/d/azuread_users"

  # ignore_missing - (optional) is a type of bool
  ignore_missing = null
  # mail_nicknames - (optional) is a type of list of string
  mail_nicknames = []
  # object_ids - (optional) is a type of list of string
  object_ids = []
  # user_principal_names - (optional) is a type of list of string
  user_principal_names = []
}
```

[top](#index)

### Variables

```terraform
variable "ignore_missing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mail_nicknames" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "object_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "user_principal_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuread_users" "this" {
  ignore_missing       = var.ignore_missing
  mail_nicknames       = var.mail_nicknames
  object_ids           = var.object_ids
  user_principal_names = var.user_principal_names
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azuread_users.this.id
}

output "mail_nicknames" {
  description = "returns a list of string"
  value       = data.azuread_users.this.mail_nicknames
}

output "object_ids" {
  description = "returns a list of string"
  value       = data.azuread_users.this.object_ids
}

output "user_principal_names" {
  description = "returns a list of string"
  value       = data.azuread_users.this.user_principal_names
}

output "users" {
  description = "returns a list of object"
  value       = data.azuread_users.this.users
}

output "this" {
  value = azuread_users.this
}
```

[top](#index)