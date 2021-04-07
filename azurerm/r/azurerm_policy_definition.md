# azurerm_policy_definition

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
module "azurerm_policy_definition" {
  source = "./modules/azurerm/r/azurerm_policy_definition"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # management_group_id - (optional) is a type of string
  management_group_id = null
  # management_group_name - (optional) is a type of string
  management_group_name = null
  # metadata - (optional) is a type of string
  metadata = null
  # mode - (required) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of string
  parameters = null
  # policy_rule - (optional) is a type of string
  policy_rule = null
  # policy_type - (required) is a type of string
  policy_type = null

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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "management_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "management_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_rule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_type" {
  description = "(required)"
  type        = string
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
resource "azurerm_policy_definition" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # management_group_id - (optional) is a type of string
  management_group_id = var.management_group_id
  # management_group_name - (optional) is a type of string
  management_group_name = var.management_group_name
  # metadata - (optional) is a type of string
  metadata = var.metadata
  # mode - (required) is a type of string
  mode = var.mode
  # name - (required) is a type of string
  name = var.name
  # parameters - (optional) is a type of string
  parameters = var.parameters
  # policy_rule - (optional) is a type of string
  policy_rule = var.policy_rule
  # policy_type - (required) is a type of string
  policy_type = var.policy_type

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
  value       = azurerm_policy_definition.this.id
}

output "management_group_id" {
  description = "returns a string"
  value       = azurerm_policy_definition.this.management_group_id
}

output "management_group_name" {
  description = "returns a string"
  value       = azurerm_policy_definition.this.management_group_name
}

output "metadata" {
  description = "returns a string"
  value       = azurerm_policy_definition.this.metadata
}

output "this" {
  value = azurerm_policy_definition.this
}
```

[top](#index)