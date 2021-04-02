# azurerm_managed_application

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
module "azurerm_managed_application" {
  source = "./modules/azurerm/r/azurerm_managed_application"

  # application_definition_id - (optional) is a type of string
  application_definition_id = null
  # kind - (required) is a type of string
  kind = null
  # location - (required) is a type of string
  location = null
  # managed_resource_group_name - (required) is a type of string
  managed_resource_group_name = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  plan = [{
    name           = null
    product        = null
    promotion_code = null
    publisher      = null
    version        = null
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
variable "application_definition_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kind" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "managed_resource_group_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
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

variable "plan" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name           = string
      product        = string
      promotion_code = string
      publisher      = string
      version        = string
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
resource "azurerm_managed_application" "this" {
  application_definition_id   = var.application_definition_id
  kind                        = var.kind
  location                    = var.location
  managed_resource_group_name = var.managed_resource_group_name
  name                        = var.name
  parameters                  = var.parameters
  resource_group_name         = var.resource_group_name
  tags                        = var.tags

  dynamic "plan" {
    for_each = var.plan
    content {
      name           = plan.value["name"]
      product        = plan.value["product"]
      promotion_code = plan.value["promotion_code"]
      publisher      = plan.value["publisher"]
      version        = plan.value["version"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
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
  value       = azurerm_managed_application.this.id
}

output "outputs" {
  description = "returns a map of string"
  value       = azurerm_managed_application.this.outputs
}

output "this" {
  value = azurerm_managed_application.this
}
```

[top](#index)