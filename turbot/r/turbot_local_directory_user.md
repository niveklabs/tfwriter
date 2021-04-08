# turbot_local_directory_user

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
module "turbot_local_directory_user" {
  source = "./modules/turbot/r/turbot_local_directory_user"

  # display_name - (required) is a type of string
  display_name = null
  # email - (required) is a type of string
  email = null
  # family_name - (optional) is a type of string
  family_name = null
  # given_name - (optional) is a type of string
  given_name = null
  # middle_name - (optional) is a type of string
  middle_name = null
  # parent - (required) is a type of string
  parent = null
  # picture - (optional) is a type of string
  picture = null
  # tags - (optional) is a type of map of string
  tags = {}
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(required)"
  type        = string
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "family_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "given_name" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "turbot_local_directory_user" "this" {
  # display_name - (required) is a type of string
  display_name = var.display_name
  # email - (required) is a type of string
  email = var.email
  # family_name - (optional) is a type of string
  family_name = var.family_name
  # given_name - (optional) is a type of string
  given_name = var.given_name
  # middle_name - (optional) is a type of string
  middle_name = var.middle_name
  # parent - (required) is a type of string
  parent = var.parent
  # picture - (optional) is a type of string
  picture = var.picture
  # tags - (optional) is a type of map of string
  tags = var.tags
  # title - (required) is a type of string
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_local_directory_user.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_local_directory_user.this.parent_akas
}

output "password_timestamp" {
  description = "returns a string"
  value       = turbot_local_directory_user.this.password_timestamp
}

output "status" {
  description = "returns a string"
  value       = turbot_local_directory_user.this.status
}

output "this" {
  value = turbot_local_directory_user.this
}
```

[top](#index)