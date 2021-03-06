# checkpoint_management_user

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_user" {
  source = "./modules/checkpoint/d/checkpoint_management_user"

  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Object name."
  type        = string
  default     = null
}

variable "uid" {
  description = "(optional) - Object unique identifier."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_user" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "allowed_locations" {
  description = "returns a map of string"
  value       = data.checkpoint_management_user.this.allowed_locations
}

output "authentication_method" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.authentication_method
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.comments
}

output "connect_daily" {
  description = "returns a bool"
  value       = data.checkpoint_management_user.this.connect_daily
}

output "connect_on_days" {
  description = "returns a set of string"
  value       = data.checkpoint_management_user.this.connect_on_days
}

output "email" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.email
}

output "encryption" {
  description = "returns a map of string"
  value       = data.checkpoint_management_user.this.encryption
}

output "expiration_date" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.expiration_date
}

output "from_hour" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.from_hour
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.id
}

output "phone_number" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.phone_number
}

output "radius_server" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.radius_server
}

output "tacacs_server" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.tacacs_server
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_user.this.tags
}

output "to_hour" {
  description = "returns a string"
  value       = data.checkpoint_management_user.this.to_hour
}

output "this" {
  value = checkpoint_management_user.this
}
```

[top](#index)