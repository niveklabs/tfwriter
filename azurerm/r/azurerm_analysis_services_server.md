# azurerm_analysis_services_server

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
module "azurerm_analysis_services_server" {
  source = "./modules/azurerm/r/azurerm_analysis_services_server"

  # admin_users - (optional) is a type of set of string
  admin_users = []
  # backup_blob_container_uri - (optional) is a type of string
  backup_blob_container_uri = null
  # enable_power_bi_service - (optional) is a type of bool
  enable_power_bi_service = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # querypool_connection_mode - (optional) is a type of string
  querypool_connection_mode = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (required) is a type of string
  sku = null
  # tags - (optional) is a type of map of string
  tags = {}

  ipv4_firewall_rule = [{
    name        = null
    range_end   = null
    range_start = null
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
variable "admin_users" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "backup_blob_container_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_power_bi_service" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "querypool_connection_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ipv4_firewall_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name        = string
      range_end   = string
      range_start = string
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
resource "azurerm_analysis_services_server" "this" {
  # admin_users - (optional) is a type of set of string
  admin_users = var.admin_users
  # backup_blob_container_uri - (optional) is a type of string
  backup_blob_container_uri = var.backup_blob_container_uri
  # enable_power_bi_service - (optional) is a type of bool
  enable_power_bi_service = var.enable_power_bi_service
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # querypool_connection_mode - (optional) is a type of string
  querypool_connection_mode = var.querypool_connection_mode
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku - (required) is a type of string
  sku = var.sku
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "ipv4_firewall_rule" {
    for_each = var.ipv4_firewall_rule
    content {
      # name - (required) is a type of string
      name = ipv4_firewall_rule.value["name"]
      # range_end - (required) is a type of string
      range_end = ipv4_firewall_rule.value["range_end"]
      # range_start - (required) is a type of string
      range_start = ipv4_firewall_rule.value["range_start"]
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
  value       = azurerm_analysis_services_server.this.id
}

output "querypool_connection_mode" {
  description = "returns a string"
  value       = azurerm_analysis_services_server.this.querypool_connection_mode
}

output "server_full_name" {
  description = "returns a string"
  value       = azurerm_analysis_services_server.this.server_full_name
}

output "this" {
  value = azurerm_analysis_services_server.this
}
```

[top](#index)