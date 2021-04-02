# azurerm_private_endpoint

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
module "azurerm_private_endpoint" {
  source = "./modules/azurerm/r/azurerm_private_endpoint"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  private_dns_zone_group = [{
    id                   = null
    name                 = null
    private_dns_zone_ids = []
  }]

  private_service_connection = [{
    is_manual_connection           = null
    name                           = null
    private_connection_resource_id = null
    private_ip_address             = null
    request_message                = null
    subresource_names              = []
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
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "private_dns_zone_group" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id                   = string
      name                 = string
      private_dns_zone_ids = list(string)
    }
  ))
  default = []
}

variable "private_service_connection" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      is_manual_connection           = bool
      name                           = string
      private_connection_resource_id = string
      private_ip_address             = string
      request_message                = string
      subresource_names              = list(string)
    }
  ))
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
resource "azurerm_private_endpoint" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  subnet_id           = var.subnet_id
  tags                = var.tags

  dynamic "private_dns_zone_group" {
    for_each = var.private_dns_zone_group
    content {
      name                 = private_dns_zone_group.value["name"]
      private_dns_zone_ids = private_dns_zone_group.value["private_dns_zone_ids"]
    }
  }

  dynamic "private_service_connection" {
    for_each = var.private_service_connection
    content {
      is_manual_connection           = private_service_connection.value["is_manual_connection"]
      name                           = private_service_connection.value["name"]
      private_connection_resource_id = private_service_connection.value["private_connection_resource_id"]
      request_message                = private_service_connection.value["request_message"]
      subresource_names              = private_service_connection.value["subresource_names"]
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
output "custom_dns_configs" {
  description = "returns a list of object"
  value       = azurerm_private_endpoint.this.custom_dns_configs
}

output "id" {
  description = "returns a string"
  value       = azurerm_private_endpoint.this.id
}

output "private_dns_zone_configs" {
  description = "returns a list of object"
  value       = azurerm_private_endpoint.this.private_dns_zone_configs
}

output "this" {
  value = azurerm_private_endpoint.this
}
```

[top](#index)