# azurerm_resources

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
module "azurerm_resources" {
  source = "./modules/azurerm/d/azurerm_resources"

  # name - (optional) is a type of string
  name = null
  # required_tags - (optional) is a type of map of string
  required_tags = {}
  # resource_group_name - (optional) is a type of string
  resource_group_name = null
  # type - (optional) is a type of string
  type = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "required_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "resource_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
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
data "azurerm_resources" "this" {
  name                = var.name
  required_tags       = var.required_tags
  resource_group_name = var.resource_group_name
  type                = var.type

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_resources.this.id
}

output "name" {
  description = "returns a string"
  value       = data.azurerm_resources.this.name
}

output "resource_group_name" {
  description = "returns a string"
  value       = data.azurerm_resources.this.resource_group_name
}

output "resources" {
  description = "returns a list of object"
  value       = data.azurerm_resources.this.resources
}

output "type" {
  description = "returns a string"
  value       = data.azurerm_resources.this.type
}

output "this" {
  value = azurerm_resources.this
}
```

[top](#index)