# azurerm_private_link_service_endpoint_connections

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_private_link_service_endpoint_connections" {
  source = "./modules/azurerm/d/azurerm_private_link_service_endpoint_connections"

  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_id - (required) is a type of string
  service_id = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "service_id" {
  description = "(required)"
  type        = string
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
data "azurerm_private_link_service_endpoint_connections" "this" {
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # service_id - (required) is a type of string
  service_id = var.service_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
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
  value       = data.azurerm_private_link_service_endpoint_connections.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_private_link_service_endpoint_connections.this.location
}

output "private_endpoint_connections" {
  description = "returns a list of object"
  value       = data.azurerm_private_link_service_endpoint_connections.this.private_endpoint_connections
}

output "service_name" {
  description = "returns a string"
  value       = data.azurerm_private_link_service_endpoint_connections.this.service_name
}

output "this" {
  value = azurerm_private_link_service_endpoint_connections.this
}
```

[top](#index)