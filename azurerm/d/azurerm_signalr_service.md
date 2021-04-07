# azurerm_signalr_service

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
module "azurerm_signalr_service" {
  source = "./modules/azurerm/d/azurerm_signalr_service"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
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
data "azurerm_signalr_service" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
output "hostname" {
  description = "returns a string"
  value       = data.azurerm_signalr_service.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_signalr_service.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.azurerm_signalr_service.this.ip_address
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_signalr_service.this.location
}

output "primary_access_key" {
  description = "returns a string"
  value       = data.azurerm_signalr_service.this.primary_access_key
  sensitive   = true
}

output "primary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_signalr_service.this.primary_connection_string
  sensitive   = true
}

output "public_port" {
  description = "returns a number"
  value       = data.azurerm_signalr_service.this.public_port
}

output "secondary_access_key" {
  description = "returns a string"
  value       = data.azurerm_signalr_service.this.secondary_access_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_signalr_service.this.secondary_connection_string
  sensitive   = true
}

output "server_port" {
  description = "returns a number"
  value       = data.azurerm_signalr_service.this.server_port
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_signalr_service.this.tags
}

output "this" {
  value = azurerm_signalr_service.this
}
```

[top](#index)