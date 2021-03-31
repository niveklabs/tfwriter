# azuread_user

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
module "azuread_user" {
  source = "./modules/azuread/d/azuread_user"

  # mail_nickname - (optional) is a type of string
  mail_nickname = null
  # object_id - (optional) is a type of string
  object_id = null
  # user_principal_name - (optional) is a type of string
  user_principal_name = null
}
```

[top](#index)

### Variables

```terraform
variable "mail_nickname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "object_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_principal_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuread_user" "this" {
  mail_nickname       = var.mail_nickname
  object_id           = var.object_id
  user_principal_name = var.user_principal_name
}
```

[top](#index)

### Outputs

```terraform
output "account_enabled" {
  description = "returns a bool"
  value       = data.azuread_user.this.account_enabled
}

output "city" {
  description = "returns a string"
  value       = data.azuread_user.this.city
}

output "company_name" {
  description = "returns a string"
  value       = data.azuread_user.this.company_name
}

output "country" {
  description = "returns a string"
  value       = data.azuread_user.this.country
}

output "department" {
  description = "returns a string"
  value       = data.azuread_user.this.department
}

output "display_name" {
  description = "returns a string"
  value       = data.azuread_user.this.display_name
}

output "given_name" {
  description = "returns a string"
  value       = data.azuread_user.this.given_name
}

output "id" {
  description = "returns a string"
  value       = data.azuread_user.this.id
}

output "immutable_id" {
  description = "returns a string"
  value       = data.azuread_user.this.immutable_id
}

output "job_title" {
  description = "returns a string"
  value       = data.azuread_user.this.job_title
}

output "mail" {
  description = "returns a string"
  value       = data.azuread_user.this.mail
}

output "mail_nickname" {
  description = "returns a string"
  value       = data.azuread_user.this.mail_nickname
}

output "mobile" {
  description = "returns a string"
  value       = data.azuread_user.this.mobile
}

output "object_id" {
  description = "returns a string"
  value       = data.azuread_user.this.object_id
}

output "onpremises_sam_account_name" {
  description = "returns a string"
  value       = data.azuread_user.this.onpremises_sam_account_name
}

output "onpremises_user_principal_name" {
  description = "returns a string"
  value       = data.azuread_user.this.onpremises_user_principal_name
}

output "physical_delivery_office_name" {
  description = "returns a string"
  value       = data.azuread_user.this.physical_delivery_office_name
}

output "postal_code" {
  description = "returns a string"
  value       = data.azuread_user.this.postal_code
}

output "state" {
  description = "returns a string"
  value       = data.azuread_user.this.state
}

output "street_address" {
  description = "returns a string"
  value       = data.azuread_user.this.street_address
}

output "surname" {
  description = "returns a string"
  value       = data.azuread_user.this.surname
}

output "usage_location" {
  description = "returns a string"
  value       = data.azuread_user.this.usage_location
}

output "user_principal_name" {
  description = "returns a string"
  value       = data.azuread_user.this.user_principal_name
}

output "this" {
  value = azuread_user.this
}
```

[top](#index)