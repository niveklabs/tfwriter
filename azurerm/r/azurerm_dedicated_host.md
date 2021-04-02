# azurerm_dedicated_host

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
module "azurerm_dedicated_host" {
  source = "./modules/azurerm/r/azurerm_dedicated_host"

  # auto_replace_on_failure - (optional) is a type of bool
  auto_replace_on_failure = null
  # dedicated_host_group_id - (required) is a type of string
  dedicated_host_group_id = null
  # license_type - (optional) is a type of string
  license_type = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # platform_fault_domain - (required) is a type of number
  platform_fault_domain = null
  # sku_name - (required) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "auto_replace_on_failure" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dedicated_host_group_id" {
  description = "(required)"
  type        = string
}

variable "license_type" {
  description = "(optional)"
  type        = string
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

variable "platform_fault_domain" {
  description = "(required)"
  type        = number
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "azurerm_dedicated_host" "this" {
  auto_replace_on_failure = var.auto_replace_on_failure
  dedicated_host_group_id = var.dedicated_host_group_id
  license_type            = var.license_type
  location                = var.location
  name                    = var.name
  platform_fault_domain   = var.platform_fault_domain
  sku_name                = var.sku_name
  tags                    = var.tags

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
  value       = azurerm_dedicated_host.this.id
}

output "this" {
  value = azurerm_dedicated_host.this
}
```

[top](#index)