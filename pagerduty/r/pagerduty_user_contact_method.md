# pagerduty_user_contact_method

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_user_contact_method" {
  source = "./modules/pagerduty/r/pagerduty_user_contact_method"

  # address - (required) is a type of string
  address = null
  # country_code - (optional) is a type of number
  country_code = null
  # label - (required) is a type of string
  label = null
  # send_short_email - (optional) is a type of bool
  send_short_email = null
  # type - (required) is a type of string
  type = null
  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required)"
  type        = string
}

variable "country_code" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "label" {
  description = "(required)"
  type        = string
}

variable "send_short_email" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "user_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_user_contact_method" "this" {
  # address - (required) is a type of string
  address = var.address
  # country_code - (optional) is a type of number
  country_code = var.country_code
  # label - (required) is a type of string
  label = var.label
  # send_short_email - (optional) is a type of bool
  send_short_email = var.send_short_email
  # type - (required) is a type of string
  type = var.type
  # user_id - (required) is a type of string
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "blacklisted" {
  description = "returns a bool"
  value       = pagerduty_user_contact_method.this.blacklisted
}

output "enabled" {
  description = "returns a bool"
  value       = pagerduty_user_contact_method.this.enabled
}

output "id" {
  description = "returns a string"
  value       = pagerduty_user_contact_method.this.id
}

output "this" {
  value = pagerduty_user_contact_method.this
}
```

[top](#index)