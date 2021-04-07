# fortios_user_group

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_group" {
  source = "./modules/fortios/r/fortios_user_group"

  # auth_concurrent_override - (optional) is a type of string
  auth_concurrent_override = null
  # auth_concurrent_value - (optional) is a type of number
  auth_concurrent_value = null
  # authtimeout - (optional) is a type of number
  authtimeout = null
  # company - (optional) is a type of string
  company = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # email - (optional) is a type of string
  email = null
  # expire - (optional) is a type of number
  expire = null
  # expire_type - (optional) is a type of string
  expire_type = null
  # fosid - (optional) is a type of number
  fosid = null
  # group_type - (optional) is a type of string
  group_type = null
  # http_digest_realm - (optional) is a type of string
  http_digest_realm = null
  # max_accounts - (optional) is a type of number
  max_accounts = null
  # mobile_phone - (optional) is a type of string
  mobile_phone = null
  # multiple_guest_add - (optional) is a type of string
  multiple_guest_add = null
  # name - (optional) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # sms_custom_server - (optional) is a type of string
  sms_custom_server = null
  # sms_server - (optional) is a type of string
  sms_server = null
  # sponsor - (optional) is a type of string
  sponsor = null
  # sso_attribute_value - (optional) is a type of string
  sso_attribute_value = null
  # user_id - (optional) is a type of string
  user_id = null
  # user_name - (optional) is a type of string
  user_name = null

  guest = [{
    comment      = null
    company      = null
    email        = null
    expiration   = null
    id           = null
    mobile_phone = null
    name         = null
    password     = null
    sponsor      = null
    user_id      = null
  }]

  match = [{
    group_name  = null
    id          = null
    server_name = null
  }]

  member = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_concurrent_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_concurrent_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "authtimeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "company" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expire" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "expire_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_digest_realm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_accounts" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mobile_phone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multiple_guest_add" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sms_custom_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sms_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sponsor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sso_attribute_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guest" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comment      = string
      company      = string
      email        = string
      expiration   = string
      id           = number
      mobile_phone = string
      name         = string
      password     = string
      sponsor      = string
      user_id      = string
    }
  ))
  default = []
}

variable "match" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      group_name  = string
      id          = number
      server_name = string
    }
  ))
  default = []
}

variable "member" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_group" "this" {
  # auth_concurrent_override - (optional) is a type of string
  auth_concurrent_override = var.auth_concurrent_override
  # auth_concurrent_value - (optional) is a type of number
  auth_concurrent_value = var.auth_concurrent_value
  # authtimeout - (optional) is a type of number
  authtimeout = var.authtimeout
  # company - (optional) is a type of string
  company = var.company
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # email - (optional) is a type of string
  email = var.email
  # expire - (optional) is a type of number
  expire = var.expire
  # expire_type - (optional) is a type of string
  expire_type = var.expire_type
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # group_type - (optional) is a type of string
  group_type = var.group_type
  # http_digest_realm - (optional) is a type of string
  http_digest_realm = var.http_digest_realm
  # max_accounts - (optional) is a type of number
  max_accounts = var.max_accounts
  # mobile_phone - (optional) is a type of string
  mobile_phone = var.mobile_phone
  # multiple_guest_add - (optional) is a type of string
  multiple_guest_add = var.multiple_guest_add
  # name - (optional) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # sms_custom_server - (optional) is a type of string
  sms_custom_server = var.sms_custom_server
  # sms_server - (optional) is a type of string
  sms_server = var.sms_server
  # sponsor - (optional) is a type of string
  sponsor = var.sponsor
  # sso_attribute_value - (optional) is a type of string
  sso_attribute_value = var.sso_attribute_value
  # user_id - (optional) is a type of string
  user_id = var.user_id
  # user_name - (optional) is a type of string
  user_name = var.user_name

  dynamic "guest" {
    for_each = var.guest
    content {
      # comment - (optional) is a type of string
      comment = guest.value["comment"]
      # company - (optional) is a type of string
      company = guest.value["company"]
      # email - (optional) is a type of string
      email = guest.value["email"]
      # expiration - (optional) is a type of string
      expiration = guest.value["expiration"]
      # id - (optional) is a type of number
      id = guest.value["id"]
      # mobile_phone - (optional) is a type of string
      mobile_phone = guest.value["mobile_phone"]
      # name - (optional) is a type of string
      name = guest.value["name"]
      # password - (optional) is a type of string
      password = guest.value["password"]
      # sponsor - (optional) is a type of string
      sponsor = guest.value["sponsor"]
      # user_id - (optional) is a type of string
      user_id = guest.value["user_id"]
    }
  }

  dynamic "match" {
    for_each = var.match
    content {
      # group_name - (optional) is a type of string
      group_name = match.value["group_name"]
      # id - (optional) is a type of number
      id = match.value["id"]
      # server_name - (optional) is a type of string
      server_name = match.value["server_name"]
    }
  }

  dynamic "member" {
    for_each = var.member
    content {
      # name - (optional) is a type of string
      name = member.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth_concurrent_override" {
  description = "returns a string"
  value       = fortios_user_group.this.auth_concurrent_override
}

output "auth_concurrent_value" {
  description = "returns a number"
  value       = fortios_user_group.this.auth_concurrent_value
}

output "authtimeout" {
  description = "returns a number"
  value       = fortios_user_group.this.authtimeout
}

output "company" {
  description = "returns a string"
  value       = fortios_user_group.this.company
}

output "email" {
  description = "returns a string"
  value       = fortios_user_group.this.email
}

output "expire" {
  description = "returns a number"
  value       = fortios_user_group.this.expire
}

output "expire_type" {
  description = "returns a string"
  value       = fortios_user_group.this.expire_type
}

output "fosid" {
  description = "returns a number"
  value       = fortios_user_group.this.fosid
}

output "group_type" {
  description = "returns a string"
  value       = fortios_user_group.this.group_type
}

output "http_digest_realm" {
  description = "returns a string"
  value       = fortios_user_group.this.http_digest_realm
}

output "id" {
  description = "returns a string"
  value       = fortios_user_group.this.id
}

output "max_accounts" {
  description = "returns a number"
  value       = fortios_user_group.this.max_accounts
}

output "mobile_phone" {
  description = "returns a string"
  value       = fortios_user_group.this.mobile_phone
}

output "multiple_guest_add" {
  description = "returns a string"
  value       = fortios_user_group.this.multiple_guest_add
}

output "name" {
  description = "returns a string"
  value       = fortios_user_group.this.name
}

output "password" {
  description = "returns a string"
  value       = fortios_user_group.this.password
}

output "sms_custom_server" {
  description = "returns a string"
  value       = fortios_user_group.this.sms_custom_server
}

output "sms_server" {
  description = "returns a string"
  value       = fortios_user_group.this.sms_server
}

output "sponsor" {
  description = "returns a string"
  value       = fortios_user_group.this.sponsor
}

output "sso_attribute_value" {
  description = "returns a string"
  value       = fortios_user_group.this.sso_attribute_value
}

output "user_id" {
  description = "returns a string"
  value       = fortios_user_group.this.user_id
}

output "user_name" {
  description = "returns a string"
  value       = fortios_user_group.this.user_name
}

output "this" {
  value = fortios_user_group.this
}
```

[top](#index)