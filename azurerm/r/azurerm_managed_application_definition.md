# azurerm_managed_application_definition

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
module "azurerm_managed_application_definition" {
  source = "./modules/azurerm/r/azurerm_managed_application_definition"

  # create_ui_definition - (optional) is a type of string
  create_ui_definition = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # location - (required) is a type of string
  location = null
  # lock_level - (required) is a type of string
  lock_level = null
  # main_template - (optional) is a type of string
  main_template = null
  # name - (required) is a type of string
  name = null
  # package_enabled - (optional) is a type of bool
  package_enabled = null
  # package_file_uri - (optional) is a type of string
  package_file_uri = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  authorization = [{
    role_definition_id   = null
    service_principal_id = null
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
variable "create_ui_definition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "lock_level" {
  description = "(required)"
  type        = string
}

variable "main_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "package_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "package_file_uri" {
  description = "(optional)"
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

variable "authorization" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      role_definition_id   = string
      service_principal_id = string
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
resource "azurerm_managed_application_definition" "this" {
  # create_ui_definition - (optional) is a type of string
  create_ui_definition = var.create_ui_definition
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # location - (required) is a type of string
  location = var.location
  # lock_level - (required) is a type of string
  lock_level = var.lock_level
  # main_template - (optional) is a type of string
  main_template = var.main_template
  # name - (required) is a type of string
  name = var.name
  # package_enabled - (optional) is a type of bool
  package_enabled = var.package_enabled
  # package_file_uri - (optional) is a type of string
  package_file_uri = var.package_file_uri
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "authorization" {
    for_each = var.authorization
    content {
      # role_definition_id - (required) is a type of string
      role_definition_id = authorization.value["role_definition_id"]
      # service_principal_id - (required) is a type of string
      service_principal_id = authorization.value["service_principal_id"]
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
  value       = azurerm_managed_application_definition.this.id
}

output "this" {
  value = azurerm_managed_application_definition.this
}
```

[top](#index)