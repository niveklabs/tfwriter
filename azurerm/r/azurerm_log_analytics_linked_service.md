# azurerm_log_analytics_linked_service

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_log_analytics_linked_service" {
  source = "./modules/azurerm/r/azurerm_log_analytics_linked_service"

  # linked_service_name - (optional) is a type of string
  linked_service_name = null
  # read_access_id - (optional) is a type of string
  read_access_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # resource_id - (optional) is a type of string
  resource_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # workspace_id - (optional) is a type of string
  workspace_id = null
  # workspace_name - (optional) is a type of string
  workspace_name = null
  # write_access_id - (optional) is a type of string
  write_access_id = null

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
variable "linked_service_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "read_access_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "workspace_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "workspace_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "write_access_id" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_log_analytics_linked_service" "this" {
  linked_service_name = var.linked_service_name
  read_access_id      = var.read_access_id
  resource_group_name = var.resource_group_name
  resource_id         = var.resource_id
  tags                = var.tags
  workspace_id        = var.workspace_id
  workspace_name      = var.workspace_name
  write_access_id     = var.write_access_id

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
  value       = azurerm_log_analytics_linked_service.this.id
}

output "linked_service_name" {
  description = "returns a string"
  value       = azurerm_log_analytics_linked_service.this.linked_service_name
}

output "name" {
  description = "returns a string"
  value       = azurerm_log_analytics_linked_service.this.name
}

output "read_access_id" {
  description = "returns a string"
  value       = azurerm_log_analytics_linked_service.this.read_access_id
}

output "resource_id" {
  description = "returns a string"
  value       = azurerm_log_analytics_linked_service.this.resource_id
}

output "workspace_id" {
  description = "returns a string"
  value       = azurerm_log_analytics_linked_service.this.workspace_id
}

output "workspace_name" {
  description = "returns a string"
  value       = azurerm_log_analytics_linked_service.this.workspace_name
}

output "this" {
  value = azurerm_log_analytics_linked_service.this
}
```

[top](#index)