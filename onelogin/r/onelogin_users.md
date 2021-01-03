# onelogin_users

[back](../onelogin.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    onelogin = ">= 0.1.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "onelogin_users" {
  source = "./modules/onelogin/r/onelogin_users"

  # comment - (optional) is a type of string
  comment = null
  # company - (optional) is a type of string
  company = null
  # department - (optional) is a type of string
  department = null
  # directory_id - (optional) is a type of number
  directory_id = null
  # distinguished_name - (optional) is a type of string
  distinguished_name = null
  # email - (required) is a type of string
  email = null
  # external_id - (optional) is a type of number
  external_id = null
  # firstname - (optional) is a type of string
  firstname = null
  # group_id - (optional) is a type of number
  group_id = null
  # lastname - (optional) is a type of string
  lastname = null
  # manager_ad_id - (optional) is a type of number
  manager_ad_id = null
  # manager_user_id - (optional) is a type of number
  manager_user_id = null
  # member_of - (optional) is a type of string
  member_of = null
  # phone - (optional) is a type of string
  phone = null
  # samaccountname - (optional) is a type of string
  samaccountname = null
  # state - (optional) is a type of number
  state = null
  # status - (optional) is a type of number
  status = null
  # title - (optional) is a type of string
  title = null
  # trusted_idp_id - (optional) is a type of number
  trusted_idp_id = null
  # username - (required) is a type of string
  username = null
  # userprincipalname - (optional) is a type of string
  userprincipalname = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "company" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "department" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "directory_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distinguished_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "external_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "firstname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lastname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "manager_ad_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "manager_user_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "member_of" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "phone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "samaccountname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "title" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusted_idp_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}

variable "userprincipalname" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "onelogin_users" "this" {
  comment            = var.comment
  company            = var.company
  department         = var.department
  directory_id       = var.directory_id
  distinguished_name = var.distinguished_name
  email              = var.email
  external_id        = var.external_id
  firstname          = var.firstname
  group_id           = var.group_id
  lastname           = var.lastname
  manager_ad_id      = var.manager_ad_id
  manager_user_id    = var.manager_user_id
  member_of          = var.member_of
  phone              = var.phone
  samaccountname     = var.samaccountname
  state              = var.state
  status             = var.status
  title              = var.title
  trusted_idp_id     = var.trusted_idp_id
  username           = var.username
  userprincipalname  = var.userprincipalname
}
```

[top](#index)

### Outputs

```terraform
output "directory_id" {
  description = "returns a number"
  value       = onelogin_users.this.directory_id
}

output "external_id" {
  description = "returns a number"
  value       = onelogin_users.this.external_id
}

output "group_id" {
  description = "returns a number"
  value       = onelogin_users.this.group_id
}

output "id" {
  description = "returns a string"
  value       = onelogin_users.this.id
}

output "manager_ad_id" {
  description = "returns a number"
  value       = onelogin_users.this.manager_ad_id
}

output "manager_user_id" {
  description = "returns a number"
  value       = onelogin_users.this.manager_user_id
}

output "state" {
  description = "returns a number"
  value       = onelogin_users.this.state
}

output "status" {
  description = "returns a number"
  value       = onelogin_users.this.status
}

output "trusted_idp_id" {
  description = "returns a number"
  value       = onelogin_users.this.trusted_idp_id
}

output "this" {
  value = onelogin_users.this
}
```

[top](#index)