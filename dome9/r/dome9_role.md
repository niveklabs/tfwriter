# dome9_role

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
module "dome9_role" {
  source = "./modules/dome9/r/dome9_role"

  # create - (optional) is a type of list of string
  create = []
  # cross_account_access - (optional) is a type of list of string
  cross_account_access = []
  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
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

variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
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
resource "dome9_role" "this" {
  # create - (optional) is a type of list of string
  create = var.create
  # cross_account_access - (optional) is a type of list of string
  cross_account_access = var.cross_account_access
  # description - (required) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # permit_alert_actions - (optional) is a type of bool
  permit_alert_actions = var.permit_alert_actions
  # permit_notifications - (optional) is a type of bool
  permit_notifications = var.permit_notifications
  # permit_on_boarding - (optional) is a type of bool
  permit_on_boarding = var.permit_on_boarding
  # permit_policies - (optional) is a type of bool
  permit_policies = var.permit_policies
  # permit_rulesets - (optional) is a type of bool
  permit_rulesets = var.permit_rulesets

  dynamic "access" {
    for_each = var.access
    content {
      # main_id - (optional) is a type of string
      main_id = access.value["main_id"]
      # region - (optional) is a type of string
      region = access.value["region"]
      # security_group_id - (optional) is a type of string
      security_group_id = access.value["security_group_id"]
      # traffic - (optional) is a type of string
      traffic = access.value["traffic"]
      # type - (optional) is a type of string
      type = access.value["type"]
    }
  }

  dynamic "manage" {
    for_each = var.manage
    content {
      # main_id - (optional) is a type of string
      main_id = manage.value["main_id"]
      # region - (optional) is a type of string
      region = manage.value["region"]
      # security_group_id - (optional) is a type of string
      security_group_id = manage.value["security_group_id"]
      # traffic - (optional) is a type of string
      traffic = manage.value["traffic"]
      # type - (optional) is a type of string
      type = manage.value["type"]
    }
  }

  dynamic "view" {
    for_each = var.view
    content {
      # main_id - (optional) is a type of string
      main_id = view.value["main_id"]
      # region - (optional) is a type of string
      region = view.value["region"]
      # security_group_id - (optional) is a type of string
      security_group_id = view.value["security_group_id"]
      # traffic - (optional) is a type of string
      traffic = view.value["traffic"]
      # type - (optional) is a type of string
      type = view.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dome9_role.this.id
}

output "this" {
  value = dome9_role.this
}
```

[top](#index)