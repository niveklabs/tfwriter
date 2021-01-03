# azurerm_network_service_tags

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_network_service_tags" {
  source = "./modules/azurerm/d/azurerm_network_service_tags"

  # location - (required) is a type of string
  location = null
  # location_filter - (optional) is a type of string
  location_filter = null
  # service - (required) is a type of string
  service = null

  timeouts = [{
    read = null
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

variable "location_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service" {
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
data "azurerm_network_service_tags" "this" {
  location        = var.location
  location_filter = var.location_filter
  service         = var.service

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
output "address_prefixes" {
  description = "returns a list of string"
  value       = data.azurerm_network_service_tags.this.address_prefixes
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_network_service_tags.this.id
}

output "this" {
  value = azurerm_network_service_tags.this
}
```

[top](#index)