# azurerm_lighthouse_assignment

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
module "azurerm_lighthouse_assignment" {
  source = "./modules/azurerm/r/azurerm_lighthouse_assignment"

  # lighthouse_definition_id - (required) is a type of string
  lighthouse_definition_id = null
  # name - (optional) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "lighthouse_definition_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_lighthouse_assignment" "this" {
  lighthouse_definition_id = var.lighthouse_definition_id
  name                     = var.name
  scope                    = var.scope

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_lighthouse_assignment.this.id
}

output "name" {
  description = "returns a string"
  value       = azurerm_lighthouse_assignment.this.name
}

output "this" {
  value = azurerm_lighthouse_assignment.this
}
```

[top](#index)