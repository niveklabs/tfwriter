# vault_database_secret_backend_static_role

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_database_secret_backend_static_role" {
  source = "./modules/vault/r/vault_database_secret_backend_static_role"

  # backend - (required) is a type of string
  backend = null
  # db_name - (required) is a type of string
  db_name = null
  # name - (required) is a type of string
  name = null
  # rotation_period - (required) is a type of number
  rotation_period = null
  # rotation_statements - (optional) is a type of list of string
  rotation_statements = []
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The path of the Database Secret Backend the role belongs to."
  type        = string
}

variable "db_name" {
  description = "(required) - Database connection to use for this role."
  type        = string
}

variable "name" {
  description = "(required) - Unique name for the static role."
  type        = string
}

variable "rotation_period" {
  description = "(required) - The amount of time Vault should wait before rotating the password, in seconds."
  type        = number
}

variable "rotation_statements" {
  description = "(optional) - Database statements to execute to rotate the password for the configured database user."
  type        = list(string)
  default     = null
}

variable "username" {
  description = "(required) - The database username that this role corresponds to."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_database_secret_backend_static_role" "this" {
  backend             = var.backend
  db_name             = var.db_name
  name                = var.name
  rotation_period     = var.rotation_period
  rotation_statements = var.rotation_statements
  username            = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_database_secret_backend_static_role.this.id
}

output "this" {
  value = vault_database_secret_backend_static_role.this
}
```

[top](#index)