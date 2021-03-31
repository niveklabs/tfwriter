# aci_local_user

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_local_user" {
  source = "./modules/aci/r/aci_local_user"

  # account_status - (optional) is a type of string
  account_status = null
  # annotation - (optional) is a type of string
  annotation = null
  # cert_attribute - (optional) is a type of string
  cert_attribute = null
  # clear_pwd_history - (optional) is a type of string
  clear_pwd_history = null
  # description - (optional) is a type of string
  description = null
  # email - (optional) is a type of string
  email = null
  # expiration - (optional) is a type of string
  expiration = null
  # expires - (optional) is a type of string
  expires = null
  # first_name - (optional) is a type of string
  first_name = null
  # last_name - (optional) is a type of string
  last_name = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # otpenable - (optional) is a type of string
  otpenable = null
  # otpkey - (optional) is a type of string
  otpkey = null
  # phone - (optional) is a type of string
  phone = null
  # pwd - (optional) is a type of string
  pwd = null
  # pwd_life_time - (optional) is a type of string
  pwd_life_time = null
  # pwd_update_required - (optional) is a type of string
  pwd_update_required = null
  # rbac_string - (optional) is a type of string
  rbac_string = null
  # unix_user_id - (optional) is a type of string
  unix_user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "account_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "clear_pwd_history" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expires" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "first_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "otpenable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "otpkey" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "phone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pwd_life_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pwd_update_required" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rbac_string" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unix_user_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_local_user" "this" {
  account_status      = var.account_status
  annotation          = var.annotation
  cert_attribute      = var.cert_attribute
  clear_pwd_history   = var.clear_pwd_history
  description         = var.description
  email               = var.email
  expiration          = var.expiration
  expires             = var.expires
  first_name          = var.first_name
  last_name           = var.last_name
  name                = var.name
  name_alias          = var.name_alias
  otpenable           = var.otpenable
  otpkey              = var.otpkey
  phone               = var.phone
  pwd                 = var.pwd
  pwd_life_time       = var.pwd_life_time
  pwd_update_required = var.pwd_update_required
  rbac_string         = var.rbac_string
  unix_user_id        = var.unix_user_id
}
```

[top](#index)

### Outputs

```terraform
output "account_status" {
  description = "returns a string"
  value       = aci_local_user.this.account_status
}

output "cert_attribute" {
  description = "returns a string"
  value       = aci_local_user.this.cert_attribute
}

output "clear_pwd_history" {
  description = "returns a string"
  value       = aci_local_user.this.clear_pwd_history
}

output "description" {
  description = "returns a string"
  value       = aci_local_user.this.description
}

output "email" {
  description = "returns a string"
  value       = aci_local_user.this.email
}

output "expiration" {
  description = "returns a string"
  value       = aci_local_user.this.expiration
}

output "expires" {
  description = "returns a string"
  value       = aci_local_user.this.expires
}

output "first_name" {
  description = "returns a string"
  value       = aci_local_user.this.first_name
}

output "id" {
  description = "returns a string"
  value       = aci_local_user.this.id
}

output "last_name" {
  description = "returns a string"
  value       = aci_local_user.this.last_name
}

output "name_alias" {
  description = "returns a string"
  value       = aci_local_user.this.name_alias
}

output "otpenable" {
  description = "returns a string"
  value       = aci_local_user.this.otpenable
}

output "otpkey" {
  description = "returns a string"
  value       = aci_local_user.this.otpkey
}

output "phone" {
  description = "returns a string"
  value       = aci_local_user.this.phone
}

output "pwd" {
  description = "returns a string"
  value       = aci_local_user.this.pwd
}

output "pwd_life_time" {
  description = "returns a string"
  value       = aci_local_user.this.pwd_life_time
}

output "pwd_update_required" {
  description = "returns a string"
  value       = aci_local_user.this.pwd_update_required
}

output "rbac_string" {
  description = "returns a string"
  value       = aci_local_user.this.rbac_string
}

output "unix_user_id" {
  description = "returns a string"
  value       = aci_local_user.this.unix_user_id
}

output "this" {
  value = aci_local_user.this
}
```

[top](#index)