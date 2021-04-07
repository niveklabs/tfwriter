# azurerm_signalr_service

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
module "azurerm_signalr_service" {
  source = "./modules/azurerm/r/azurerm_signalr_service"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  cors = [{
    allowed_origins = []
  }]

  features = [{
    flag  = null
    value = null
  }]

  sku = [{
    capacity = null
    name     = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  upstream_endpoint = [{
    category_pattern = []
    event_pattern    = []
    hub_pattern      = []
    url_template     = null
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "cors" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allowed_origins = set(string)
    }
  ))
  default = []
}

variable "features" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      flag  = string
      value = string
    }
  ))
  default = []
}

variable "sku" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      capacity = number
      name     = string
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

variable "upstream_endpoint" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      category_pattern = list(string)
      event_pattern    = list(string)
      hub_pattern      = list(string)
      url_template     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_signalr_service" "this" {
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "cors" {
    for_each = var.cors
    content {
      # allowed_origins - (required) is a type of set of string
      allowed_origins = cors.value["allowed_origins"]
    }
  }

  dynamic "features" {
    for_each = var.features
    content {
      # flag - (required) is a type of string
      flag = features.value["flag"]
      # value - (required) is a type of string
      value = features.value["value"]
    }
  }

  dynamic "sku" {
    for_each = var.sku
    content {
      # capacity - (required) is a type of number
      capacity = sku.value["capacity"]
      # name - (required) is a type of string
      name = sku.value["name"]
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

  dynamic "upstream_endpoint" {
    for_each = var.upstream_endpoint
    content {
      # category_pattern - (required) is a type of list of string
      category_pattern = upstream_endpoint.value["category_pattern"]
      # event_pattern - (required) is a type of list of string
      event_pattern = upstream_endpoint.value["event_pattern"]
      # hub_pattern - (required) is a type of list of string
      hub_pattern = upstream_endpoint.value["hub_pattern"]
      # url_template - (required) is a type of string
      url_template = upstream_endpoint.value["url_template"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "hostname" {
  description = "returns a string"
  value       = azurerm_signalr_service.this.hostname
}

output "id" {
  description = "returns a string"
  value       = azurerm_signalr_service.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = azurerm_signalr_service.this.ip_address
}

output "primary_access_key" {
  description = "returns a string"
  value       = azurerm_signalr_service.this.primary_access_key
  sensitive   = true
}

output "primary_connection_string" {
  description = "returns a string"
  value       = azurerm_signalr_service.this.primary_connection_string
  sensitive   = true
}

output "public_port" {
  description = "returns a number"
  value       = azurerm_signalr_service.this.public_port
}

output "secondary_access_key" {
  description = "returns a string"
  value       = azurerm_signalr_service.this.secondary_access_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = azurerm_signalr_service.this.secondary_connection_string
  sensitive   = true
}

output "server_port" {
  description = "returns a number"
  value       = azurerm_signalr_service.this.server_port
}

output "this" {
  value = azurerm_signalr_service.this
}
```

[top](#index)