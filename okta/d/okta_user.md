# okta_user

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "okta_user" {
  source = "./modules/okta/d/okta_user"

  # user_id - (optional) is a type of string
  user_id = null

  search = [{
    comparison = null
    name       = null
    value      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "user_id" {
  description = "(optional) - Retrieve a single user based on their id"
  type        = string
  default     = null
}

variable "search" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      comparison = string
      name       = string
      value      = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "okta_user" "this" {
  user_id = var.user_id

  dynamic "search" {
    for_each = var.search
    content {
      comparison = search.value["comparison"]
      name       = search.value["name"]
      value      = search.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "admin_roles" {
  description = "returns a set of string"
  value       = data.okta_user.this.admin_roles
}

output "city" {
  description = "returns a string"
  value       = data.okta_user.this.city
}

output "cost_center" {
  description = "returns a string"
  value       = data.okta_user.this.cost_center
}

output "country_code" {
  description = "returns a string"
  value       = data.okta_user.this.country_code
}

output "custom_profile_attributes" {
  description = "returns a string"
  value       = data.okta_user.this.custom_profile_attributes
}

output "department" {
  description = "returns a string"
  value       = data.okta_user.this.department
}

output "display_name" {
  description = "returns a string"
  value       = data.okta_user.this.display_name
}

output "division" {
  description = "returns a string"
  value       = data.okta_user.this.division
}

output "email" {
  description = "returns a string"
  value       = data.okta_user.this.email
}

output "employee_number" {
  description = "returns a string"
  value       = data.okta_user.this.employee_number
}

output "first_name" {
  description = "returns a string"
  value       = data.okta_user.this.first_name
}

output "group_memberships" {
  description = "returns a set of string"
  value       = data.okta_user.this.group_memberships
}

output "honorific_prefix" {
  description = "returns a string"
  value       = data.okta_user.this.honorific_prefix
}

output "honorific_suffix" {
  description = "returns a string"
  value       = data.okta_user.this.honorific_suffix
}

output "id" {
  description = "returns a string"
  value       = data.okta_user.this.id
}

output "last_name" {
  description = "returns a string"
  value       = data.okta_user.this.last_name
}

output "locale" {
  description = "returns a string"
  value       = data.okta_user.this.locale
}

output "login" {
  description = "returns a string"
  value       = data.okta_user.this.login
}

output "manager" {
  description = "returns a string"
  value       = data.okta_user.this.manager
}

output "manager_id" {
  description = "returns a string"
  value       = data.okta_user.this.manager_id
}

output "middle_name" {
  description = "returns a string"
  value       = data.okta_user.this.middle_name
}

output "mobile_phone" {
  description = "returns a string"
  value       = data.okta_user.this.mobile_phone
}

output "nick_name" {
  description = "returns a string"
  value       = data.okta_user.this.nick_name
}

output "organization" {
  description = "returns a string"
  value       = data.okta_user.this.organization
}

output "postal_address" {
  description = "returns a string"
  value       = data.okta_user.this.postal_address
}

output "preferred_language" {
  description = "returns a string"
  value       = data.okta_user.this.preferred_language
}

output "primary_phone" {
  description = "returns a string"
  value       = data.okta_user.this.primary_phone
}

output "profile_url" {
  description = "returns a string"
  value       = data.okta_user.this.profile_url
}

output "second_email" {
  description = "returns a string"
  value       = data.okta_user.this.second_email
}

output "state" {
  description = "returns a string"
  value       = data.okta_user.this.state
}

output "status" {
  description = "returns a string"
  value       = data.okta_user.this.status
}

output "street_address" {
  description = "returns a string"
  value       = data.okta_user.this.street_address
}

output "timezone" {
  description = "returns a string"
  value       = data.okta_user.this.timezone
}

output "title" {
  description = "returns a string"
  value       = data.okta_user.this.title
}

output "user_type" {
  description = "returns a string"
  value       = data.okta_user.this.user_type
}

output "zip_code" {
  description = "returns a string"
  value       = data.okta_user.this.zip_code
}

output "this" {
  value = okta_user.this
}
```

[top](#index)