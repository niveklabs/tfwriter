# ovh_me_identity_user

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_identity_user" {
  source = "./modules/ovh/d/ovh_me_identity_user"

  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```terraform
variable "user" {
  description = "(required) - User's login"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ovh_me_identity_user" "this" {
  user = var.user
}
```

[top](#index)

### Outputs

```terraform
output "creation" {
  description = "returns a string"
  value       = data.ovh_me_identity_user.this.creation
}

output "description" {
  description = "returns a string"
  value       = data.ovh_me_identity_user.this.description
}

output "email" {
  description = "returns a string"
  value       = data.ovh_me_identity_user.this.email
}

output "group" {
  description = "returns a string"
  value       = data.ovh_me_identity_user.this.group
}

output "id" {
  description = "returns a string"
  value       = data.ovh_me_identity_user.this.id
}

output "last_update" {
  description = "returns a string"
  value       = data.ovh_me_identity_user.this.last_update
}

output "login" {
  description = "returns a string"
  value       = data.ovh_me_identity_user.this.login
}

output "password_last_update" {
  description = "returns a string"
  value       = data.ovh_me_identity_user.this.password_last_update
}

output "status" {
  description = "returns a string"
  value       = data.ovh_me_identity_user.this.status
}

output "this" {
  value = ovh_me_identity_user.this
}
```

[top](#index)