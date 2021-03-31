# azurerm_maintenance_assignment_dedicated_host

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_maintenance_assignment_dedicated_host" {
  source = "./modules/azurerm/r/azurerm_maintenance_assignment_dedicated_host"

  # dedicated_host_id - (required) is a type of string
  dedicated_host_id = null
  # location - (required) is a type of string
  location = null
  # maintenance_configuration_id - (required) is a type of string
  maintenance_configuration_id = null

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
variable "dedicated_host_id" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "maintenance_configuration_id" {
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
resource "azurerm_maintenance_assignment_dedicated_host" "this" {
  dedicated_host_id            = var.dedicated_host_id
  location                     = var.location
  maintenance_configuration_id = var.maintenance_configuration_id

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
  value       = azurerm_maintenance_assignment_dedicated_host.this.id
}

output "this" {
  value = azurerm_maintenance_assignment_dedicated_host.this
}
```

[top](#index)