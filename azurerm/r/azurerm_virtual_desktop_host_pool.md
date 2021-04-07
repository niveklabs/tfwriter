# azurerm_virtual_desktop_host_pool

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_virtual_desktop_host_pool" {
  source = "./modules/azurerm/r/azurerm_virtual_desktop_host_pool"

  # custom_rdp_properties - (optional) is a type of string
  custom_rdp_properties = null
  # description - (optional) is a type of string
  description = null
  # friendly_name - (optional) is a type of string
  friendly_name = null
  # load_balancer_type - (required) is a type of string
  load_balancer_type = null
  # location - (required) is a type of string
  location = null
  # maximum_sessions_allowed - (optional) is a type of number
  maximum_sessions_allowed = null
  # name - (required) is a type of string
  name = null
  # personal_desktop_assignment_type - (optional) is a type of string
  personal_desktop_assignment_type = null
  # preferred_app_group_type - (optional) is a type of string
  preferred_app_group_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
  # validate_environment - (optional) is a type of bool
  validate_environment = null

  registration_info = [{
    expiration_date = null
    reset_token     = null
    token           = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "custom_rdp_properties" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "friendly_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_type" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "maximum_sessions_allowed" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "personal_desktop_assignment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_app_group_type" {
  description = "(optional) - Preferred App Group type to display"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "validate_environment" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "registration_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      expiration_date = string
      reset_token     = bool
      token           = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_virtual_desktop_host_pool" "this" {
  # custom_rdp_properties - (optional) is a type of string
  custom_rdp_properties = var.custom_rdp_properties
  # description - (optional) is a type of string
  description = var.description
  # friendly_name - (optional) is a type of string
  friendly_name = var.friendly_name
  # load_balancer_type - (required) is a type of string
  load_balancer_type = var.load_balancer_type
  # location - (required) is a type of string
  location = var.location
  # maximum_sessions_allowed - (optional) is a type of number
  maximum_sessions_allowed = var.maximum_sessions_allowed
  # name - (required) is a type of string
  name = var.name
  # personal_desktop_assignment_type - (optional) is a type of string
  personal_desktop_assignment_type = var.personal_desktop_assignment_type
  # preferred_app_group_type - (optional) is a type of string
  preferred_app_group_type = var.preferred_app_group_type
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type
  # validate_environment - (optional) is a type of bool
  validate_environment = var.validate_environment

  dynamic "registration_info" {
    for_each = var.registration_info
    content {
      # expiration_date - (required) is a type of string
      expiration_date = registration_info.value["expiration_date"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_virtual_desktop_host_pool.this.id
}

output "this" {
  value = azurerm_virtual_desktop_host_pool.this
}
```

[top](#index)