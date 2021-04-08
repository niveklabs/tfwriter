# turbot_profile

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    turbot = ">= 1.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "turbot_profile" {
  source = "./modules/turbot/r/turbot_profile"

  # directory_pool_id - (optional) is a type of string
  directory_pool_id = null
  # display_name - (required) is a type of string
  display_name = null
  # email - (required) is a type of string
  email = null
  # external_id - (optional) is a type of string
  external_id = null
  # family_name - (required) is a type of string
  family_name = null
  # given_name - (required) is a type of string
  given_name = null
  # last_login_timestamp - (optional) is a type of string
  last_login_timestamp = null
  # middle_name - (optional) is a type of string
  middle_name = null
  # parent - (required) is a type of string
  parent = null
  # picture - (optional) is a type of string
  picture = null
  # profile_id - (required) is a type of string
  profile_id = null
  # status - (optional) is a type of string
  status = null
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "directory_pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "external_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "family_name" {
  description = "(required)"
  type        = string
}

variable "given_name" {
  description = "(required)"
  type        = string
}

variable "last_login_timestamp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "middle_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent" {
  description = "(required)"
  type        = string
}

variable "picture" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_id" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "title" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "turbot_profile" "this" {
  # directory_pool_id - (optional) is a type of string
  directory_pool_id = var.directory_pool_id
  # display_name - (required) is a type of string
  display_name = var.display_name
  # email - (required) is a type of string
  email = var.email
  # external_id - (optional) is a type of string
  external_id = var.external_id
  # family_name - (required) is a type of string
  family_name = var.family_name
  # given_name - (required) is a type of string
  given_name = var.given_name
  # last_login_timestamp - (optional) is a type of string
  last_login_timestamp = var.last_login_timestamp
  # middle_name - (optional) is a type of string
  middle_name = var.middle_name
  # parent - (required) is a type of string
  parent = var.parent
  # picture - (optional) is a type of string
  picture = var.picture
  # profile_id - (required) is a type of string
  profile_id = var.profile_id
  # status - (optional) is a type of string
  status = var.status
  # title - (required) is a type of string
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_profile.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_profile.this.parent_akas
}

output "this" {
  value = turbot_profile.this
}
```

[top](#index)