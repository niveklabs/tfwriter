# azurerm_subnet

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
module "azurerm_subnet" {
  source = "./modules/azurerm/d/azurerm_subnet"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # virtual_network_name - (required) is a type of string
  virtual_network_name = null

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

variable "virtual_network_name" {
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
data "azurerm_subnet" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # virtual_network_name - (required) is a type of string
  virtual_network_name = var.virtual_network_name

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
output "address_prefix" {
  description = "returns a string"
  value       = data.azurerm_subnet.this.address_prefix
}

output "address_prefixes" {
  description = "returns a list of string"
  value       = data.azurerm_subnet.this.address_prefixes
}

output "enforce_private_link_endpoint_network_policies" {
  description = "returns a bool"
  value       = data.azurerm_subnet.this.enforce_private_link_endpoint_network_policies
}

output "enforce_private_link_service_network_policies" {
  description = "returns a bool"
  value       = data.azurerm_subnet.this.enforce_private_link_service_network_policies
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_subnet.this.id
}

output "network_security_group_id" {
  description = "returns a string"
  value       = data.azurerm_subnet.this.network_security_group_id
}

output "route_table_id" {
  description = "returns a string"
  value       = data.azurerm_subnet.this.route_table_id
}

output "service_endpoints" {
  description = "returns a list of string"
  value       = data.azurerm_subnet.this.service_endpoints
}

output "this" {
  value = azurerm_subnet.this
}
```

[top](#index)