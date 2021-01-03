# fortios_switchcontroller_vlan

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontroller_vlan" {
  source = "./modules/fortios/r/fortios_switchcontroller_vlan"

  # auth - (optional) is a type of string
  auth = null
  # color - (optional) is a type of number
  color = null
  # comments - (optional) is a type of string
  comments = null
  # name - (optional) is a type of string
  name = null
  # portal_message_override_group - (optional) is a type of string
  portal_message_override_group = null
  # radius_server - (optional) is a type of string
  radius_server = null
  # security - (optional) is a type of string
  security = null
  # usergroup - (optional) is a type of string
  usergroup = null
  # vdom - (optional) is a type of string
  vdom = null
  # vlanid - (optional) is a type of number
  vlanid = null

  portal_message_overrides = [{
    auth_disclaimer_page   = null
    auth_login_failed_page = null
    auth_login_page        = null
    auth_reject_page       = null
  }]

  selected_usergroups = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "color" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "portal_message_override_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usergroup" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlanid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "portal_message_overrides" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_disclaimer_page   = string
      auth_login_failed_page = string
      auth_login_page        = string
      auth_reject_page       = string
    }
  ))
  default = []
}

variable "selected_usergroups" {
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
resource "fortios_switchcontroller_vlan" "this" {
  auth                          = var.auth
  color                         = var.color
  comments                      = var.comments
  name                          = var.name
  portal_message_override_group = var.portal_message_override_group
  radius_server                 = var.radius_server
  security                      = var.security
  usergroup                     = var.usergroup
  vdom                          = var.vdom
  vlanid                        = var.vlanid

  dynamic "portal_message_overrides" {
    for_each = var.portal_message_overrides
    content {
      auth_disclaimer_page   = portal_message_overrides.value["auth_disclaimer_page"]
      auth_login_failed_page = portal_message_overrides.value["auth_login_failed_page"]
      auth_login_page        = portal_message_overrides.value["auth_login_page"]
      auth_reject_page       = portal_message_overrides.value["auth_reject_page"]
    }
  }

  dynamic "selected_usergroups" {
    for_each = var.selected_usergroups
    content {
      name = selected_usergroups.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlan.this.auth
}

output "color" {
  description = "returns a number"
  value       = fortios_switchcontroller_vlan.this.color
}

output "comments" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlan.this.comments
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlan.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlan.this.name
}

output "portal_message_override_group" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlan.this.portal_message_override_group
}

output "radius_server" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlan.this.radius_server
}

output "security" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlan.this.security
}

output "usergroup" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlan.this.usergroup
}

output "vdom" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlan.this.vdom
}

output "vlanid" {
  description = "returns a number"
  value       = fortios_switchcontroller_vlan.this.vlanid
}

output "this" {
  value = fortios_switchcontroller_vlan.this
}
```

[top](#index)