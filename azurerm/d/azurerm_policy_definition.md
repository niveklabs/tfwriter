# azurerm_policy_definition

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_policy_definition" {
  source = "./modules/azurerm/d/azurerm_policy_definition"

  # display_name - (optional) is a type of string
  display_name = null
  # management_group_id - (optional) is a type of string
  management_group_id = null
  # management_group_name - (optional) is a type of string
  management_group_name = null
  # name - (optional) is a type of string
  name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_policy_definition" "this" {
  display_name          = var.display_name
  management_group_id   = var.management_group_id
  management_group_name = var.management_group_name
  name                  = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.azurerm_policy_definition.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.azurerm_policy_definition.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_policy_definition.this.id
}

output "metadata" {
  description = "returns a string"
  value       = data.azurerm_policy_definition.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.azurerm_policy_definition.this.name
}

output "parameters" {
  description = "returns a string"
  value       = data.azurerm_policy_definition.this.parameters
}

output "policy_rule" {
  description = "returns a string"
  value       = data.azurerm_policy_definition.this.policy_rule
}

output "policy_type" {
  description = "returns a string"
  value       = data.azurerm_policy_definition.this.policy_type
}

output "type" {
  description = "returns a string"
  value       = data.azurerm_policy_definition.this.type
}

output "this" {
  value = azurerm_policy_definition.this
}
```

[top](#index)