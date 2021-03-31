# ad_user

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_user" {
  source = "./modules/ad/d/ad_user"

  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "user_id" {
  description = "(required) - The user's identifier. It can be the group's GUID, SID, Distinguished Name, or SAM Account Name."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ad_user" "this" {
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "city" {
  description = "returns a string"
  value       = data.ad_user.this.city
}

output "company" {
  description = "returns a string"
  value       = data.ad_user.this.company
}

output "country" {
  description = "returns a string"
  value       = data.ad_user.this.country
}

output "department" {
  description = "returns a string"
  value       = data.ad_user.this.department
}

output "description" {
  description = "returns a string"
  value       = data.ad_user.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.ad_user.this.display_name
}

output "division" {
  description = "returns a string"
  value       = data.ad_user.this.division
}

output "email_address" {
  description = "returns a string"
  value       = data.ad_user.this.email_address
}

output "employee_id" {
  description = "returns a string"
  value       = data.ad_user.this.employee_id
}

output "employee_number" {
  description = "returns a string"
  value       = data.ad_user.this.employee_number
}

output "fax" {
  description = "returns a string"
  value       = data.ad_user.this.fax
}

output "given_name" {
  description = "returns a string"
  value       = data.ad_user.this.given_name
}

output "home_directory" {
  description = "returns a string"
  value       = data.ad_user.this.home_directory
}

output "home_drive" {
  description = "returns a string"
  value       = data.ad_user.this.home_drive
}

output "home_page" {
  description = "returns a string"
  value       = data.ad_user.this.home_page
}

output "home_phone" {
  description = "returns a string"
  value       = data.ad_user.this.home_phone
}

output "id" {
  description = "returns a string"
  value       = data.ad_user.this.id
}

output "initials" {
  description = "returns a string"
  value       = data.ad_user.this.initials
}

output "mobile_phone" {
  description = "returns a string"
  value       = data.ad_user.this.mobile_phone
}

output "office" {
  description = "returns a string"
  value       = data.ad_user.this.office
}

output "office_phone" {
  description = "returns a string"
  value       = data.ad_user.this.office_phone
}

output "organization" {
  description = "returns a string"
  value       = data.ad_user.this.organization
}

output "other_name" {
  description = "returns a string"
  value       = data.ad_user.this.other_name
}

output "po_box" {
  description = "returns a string"
  value       = data.ad_user.this.po_box
}

output "postal_code" {
  description = "returns a string"
  value       = data.ad_user.this.postal_code
}

output "principal_name" {
  description = "returns a string"
  value       = data.ad_user.this.principal_name
}

output "sam_account_name" {
  description = "returns a string"
  value       = data.ad_user.this.sam_account_name
}

output "smart_card_logon_required" {
  description = "returns a bool"
  value       = data.ad_user.this.smart_card_logon_required
}

output "state" {
  description = "returns a string"
  value       = data.ad_user.this.state
}

output "street_address" {
  description = "returns a string"
  value       = data.ad_user.this.street_address
}

output "surname" {
  description = "returns a string"
  value       = data.ad_user.this.surname
}

output "title" {
  description = "returns a string"
  value       = data.ad_user.this.title
}

output "trusted_for_delegation" {
  description = "returns a bool"
  value       = data.ad_user.this.trusted_for_delegation
}

output "this" {
  value = ad_user.this
}
```

[top](#index)