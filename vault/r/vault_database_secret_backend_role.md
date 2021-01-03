# vault_database_secret_backend_role

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
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_database_secret_backend_role" {
  source = "./modules/vault/r/vault_database_secret_backend_role"

  # backend - (required) is a type of string
  backend = null
  # creation_statements - (required) is a type of list of string
  creation_statements = []
  # db_name - (required) is a type of string
  db_name = null
  # default_ttl - (optional) is a type of number
  default_ttl = null
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # name - (required) is a type of string
  name = null
  # renew_statements - (optional) is a type of list of string
  renew_statements = []
  # revocation_statements - (optional) is a type of list of string
  revocation_statements = []
  # rollback_statements - (optional) is a type of list of string
  rollback_statements = []
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The path of the Database Secret Backend the role belongs to."
  type        = string
}

variable "creation_statements" {
  description = "(required) - Database statements to execute to create and configure a user."
  type        = list(string)
}

variable "db_name" {
  description = "(required) - Database connection to use for this role."
  type        = string
}

variable "default_ttl" {
  description = "(optional) - Default TTL for leases associated with this role, in seconds."
  type        = number
  default     = null
}

variable "max_ttl" {
  description = "(optional) - Maximum TTL for leases associated with this role, in seconds."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Unique name for the role."
  type        = string
}

variable "renew_statements" {
  description = "(optional) - Database statements to execute to renew a user."
  type        = list(string)
  default     = null
}

variable "revocation_statements" {
  description = "(optional) - Database statements to execute to revoke a user."
  type        = list(string)
  default     = null
}

variable "rollback_statements" {
  description = "(optional) - Database statements to execute to rollback a create operation in the event of an error."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_database_secret_backend_role" "this" {
  backend               = var.backend
  creation_statements   = var.creation_statements
  db_name               = var.db_name
  default_ttl           = var.default_ttl
  max_ttl               = var.max_ttl
  name                  = var.name
  renew_statements      = var.renew_statements
  revocation_statements = var.revocation_statements
  rollback_statements   = var.rollback_statements
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_database_secret_backend_role.this.id
}

output "this" {
  value = vault_database_secret_backend_role.this
}
```

[top](#index)