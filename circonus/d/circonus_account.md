# circonus_account

[back](../circonus.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    circonus = ">= 0.12.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "circonus_account" {
  source = "./modules/circonus/d/circonus_account"

  # current - (optional) is a type of bool
  current = null
}
```

[top](#index)

### Variables

```terraform
variable "current" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "circonus_account" "this" {
  # current - (optional) is a type of bool
  current = var.current
}
```

[top](#index)

### Outputs

```terraform
output "address1" {
  description = "returns a string"
  value       = data.circonus_account.this.address1
}

output "address2" {
  description = "returns a string"
  value       = data.circonus_account.this.address2
}

output "cc_email" {
  description = "returns a string"
  value       = data.circonus_account.this.cc_email
}

output "city" {
  description = "returns a string"
  value       = data.circonus_account.this.city
}

output "contact_groups" {
  description = "returns a list of string"
  value       = data.circonus_account.this.contact_groups
}

output "country" {
  description = "returns a string"
  value       = data.circonus_account.this.country
}

output "current" {
  description = "returns a bool"
  value       = data.circonus_account.this.current
}

output "description" {
  description = "returns a string"
  value       = data.circonus_account.this.description
}

output "id" {
  description = "returns a string"
  value       = data.circonus_account.this.id
}

output "invites" {
  description = "returns a list of object"
  value       = data.circonus_account.this.invites
}

output "name" {
  description = "returns a string"
  value       = data.circonus_account.this.name
}

output "owner" {
  description = "returns a string"
  value       = data.circonus_account.this.owner
}

output "state" {
  description = "returns a string"
  value       = data.circonus_account.this.state
}

output "timezone" {
  description = "returns a string"
  value       = data.circonus_account.this.timezone
}

output "ui_base_url" {
  description = "returns a string"
  value       = data.circonus_account.this.ui_base_url
}

output "usage" {
  description = "returns a list of object"
  value       = data.circonus_account.this.usage
}

output "users" {
  description = "returns a list of object"
  value       = data.circonus_account.this.users
}

output "this" {
  value = circonus_account.this
}
```

[top](#index)