# azurerm_subnet

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
module "azurerm_subnet" {
  source = "./modules/azurerm/r/azurerm_subnet"

  # address_prefix - (optional) is a type of string
  address_prefix = null
  # address_prefixes - (optional) is a type of list of string
  address_prefixes = []
  # enforce_private_link_endpoint_network_policies - (optional) is a type of bool
  enforce_private_link_endpoint_network_policies = null
  # enforce_private_link_service_network_policies - (optional) is a type of bool
  enforce_private_link_service_network_policies = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_endpoint_policy_ids - (optional) is a type of set of string
  service_endpoint_policy_ids = []
  # service_endpoints - (optional) is a type of list of string
  service_endpoints = []
  # virtual_network_name - (required) is a type of string
  virtual_network_name = null

  delegation = [{
    name = null
    service_delegation = [{
      actions = []
      name    = null
    }]
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
variable "address_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "address_prefixes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "enforce_private_link_endpoint_network_policies" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enforce_private_link_service_network_policies" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "service_endpoint_policy_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "service_endpoints" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "virtual_network_name" {
  description = "(required)"
  type        = string
}

variable "delegation" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      service_delegation = list(object(
        {
          actions = list(string)
          name    = string
        }
      ))
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
resource "azurerm_subnet" "this" {
  address_prefix                                 = var.address_prefix
  address_prefixes                               = var.address_prefixes
  enforce_private_link_endpoint_network_policies = var.enforce_private_link_endpoint_network_policies
  enforce_private_link_service_network_policies  = var.enforce_private_link_service_network_policies
  name                                           = var.name
  resource_group_name                            = var.resource_group_name
  service_endpoint_policy_ids                    = var.service_endpoint_policy_ids
  service_endpoints                              = var.service_endpoints
  virtual_network_name                           = var.virtual_network_name

  dynamic "delegation" {
    for_each = var.delegation
    content {
      name = delegation.value["name"]

      dynamic "service_delegation" {
        for_each = delegation.value.service_delegation
        content {
          actions = service_delegation.value["actions"]
          name    = service_delegation.value["name"]
        }
      }

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
output "address_prefix" {
  description = "returns a string"
  value       = azurerm_subnet.this.address_prefix
}

output "address_prefixes" {
  description = "returns a list of string"
  value       = azurerm_subnet.this.address_prefixes
}

output "id" {
  description = "returns a string"
  value       = azurerm_subnet.this.id
}

output "this" {
  value = azurerm_subnet.this
}
```

[top](#index)