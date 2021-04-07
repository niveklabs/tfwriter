# dome9_user

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_user" {
  source = "./modules/dome9/r/dome9_user"

  # create - (optional) is a type of list of string
  create = []
  # cross_account_access - (optional) is a type of list of string
  cross_account_access = []
  # email - (required) is a type of string
  email = null
  # first_name - (required) is a type of string
  first_name = null
  # is_owner - (optional) is a type of bool
  is_owner = null
  # is_sso_enabled - (required) is a type of bool
  is_sso_enabled = null
  # last_name - (required) is a type of string
  last_name = null
  # permit_alert_actions - (optional) is a type of bool
  permit_alert_actions = null
  # permit_notifications - (optional) is a type of bool
  permit_notifications = null
  # permit_on_boarding - (optional) is a type of bool
  permit_on_boarding = null
  # permit_policies - (optional) is a type of bool
  permit_policies = null
  # permit_rulesets - (optional) is a type of bool
  permit_rulesets = null
  # role_ids - (optional) is a type of list of number
  role_ids = []

  access = [{
    main_id           = null
    region            = null
    security_group_id = null
    traffic           = null
    type              = null
  }]

  manage = [{
    main_id           = null
    region            = null
    security_group_id = null
    traffic           = null
    type              = null
  }]

  view = [{
    main_id           = null
    region            = null
    security_group_id = null
    traffic           = null
    type              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "create" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "cross_account_access" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "first_name" {
  description = "(required)"
  type        = string
}

variable "is_owner" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_sso_enabled" {
  description = "(required)"
  type        = bool
}

variable "last_name" {
  description = "(required)"
  type        = string
}

variable "permit_alert_actions" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "permit_notifications" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "permit_on_boarding" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "permit_policies" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "permit_rulesets" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "role_ids" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "access" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      main_id           = string
      region            = string
      security_group_id = string
      traffic           = string
      type              = string
    }
  ))
  default = []
}

variable "manage" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      main_id           = string
      region            = string
      security_group_id = string
      traffic           = string
      type              = string
    }
  ))
  default = []
}

variable "view" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      main_id           = string
      region            = string
      security_group_id = string
      traffic           = string
      type              = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "dome9_user" "this" {
  create               = var.create
  cross_account_access = var.cross_account_access
  email                = var.email
  first_name           = var.first_name
  is_owner             = var.is_owner
  is_sso_enabled       = var.is_sso_enabled
  last_name            = var.last_name
  permit_alert_actions = var.permit_alert_actions
  permit_notifications = var.permit_notifications
  permit_on_boarding   = var.permit_on_boarding
  permit_policies      = var.permit_policies
  permit_rulesets      = var.permit_rulesets
  role_ids             = var.role_ids

  dynamic "access" {
    for_each = var.access
    content {
      main_id           = access.value["main_id"]
      region            = access.value["region"]
      security_group_id = access.value["security_group_id"]
      traffic           = access.value["traffic"]
      type              = access.value["type"]
    }
  }

  dynamic "manage" {
    for_each = var.manage
    content {
      main_id           = manage.value["main_id"]
      region            = manage.value["region"]
      security_group_id = manage.value["security_group_id"]
      traffic           = manage.value["traffic"]
      type              = manage.value["type"]
    }
  }

  dynamic "view" {
    for_each = var.view
    content {
      main_id           = view.value["main_id"]
      region            = view.value["region"]
      security_group_id = view.value["security_group_id"]
      traffic           = view.value["traffic"]
      type              = view.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "can_switch_role" {
  description = "returns a bool"
  value       = dome9_user.this.can_switch_role
}

output "has_api_key" {
  description = "returns a bool"
  value       = dome9_user.this.has_api_key
}

output "has_api_key_v1" {
  description = "returns a bool"
  value       = dome9_user.this.has_api_key_v1
}

output "has_api_key_v2" {
  description = "returns a bool"
  value       = dome9_user.this.has_api_key_v2
}

output "iam_safe" {
  description = "returns a set of object"
  value       = dome9_user.this.iam_safe
}

output "id" {
  description = "returns a string"
  value       = dome9_user.this.id
}

output "is_auditor" {
  description = "returns a bool"
  value       = dome9_user.this.is_auditor
}

output "is_locked" {
  description = "returns a bool"
  value       = dome9_user.this.is_locked
}

output "is_mfa_enabled" {
  description = "returns a bool"
  value       = dome9_user.this.is_mfa_enabled
}

output "is_mobile_device_paired" {
  description = "returns a bool"
  value       = dome9_user.this.is_mobile_device_paired
}

output "is_owner" {
  description = "returns a bool"
  value       = dome9_user.this.is_owner
}

output "is_super_user" {
  description = "returns a bool"
  value       = dome9_user.this.is_super_user
}

output "is_suspended" {
  description = "returns a bool"
  value       = dome9_user.this.is_suspended
}

output "last_login" {
  description = "returns a string"
  value       = dome9_user.this.last_login
}

output "role_ids" {
  description = "returns a list of number"
  value       = dome9_user.this.role_ids
}

output "this" {
  value = dome9_user.this
}
```

[top](#index)