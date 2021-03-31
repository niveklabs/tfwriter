# azurerm_public_ips

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_public_ips" {
  source = "./modules/azurerm/d/azurerm_public_ips"

  # allocation_type - (optional) is a type of string
  allocation_type = null
  # attached - (optional) is a type of bool
  attached = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
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
variable "allocation_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "attached" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
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
data "azurerm_public_ips" "this" {
  allocation_type     = var.allocation_type
  attached            = var.attached
  name_prefix         = var.name_prefix
  resource_group_name = var.resource_group_name

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_public_ips.this.id
}

output "public_ips" {
  description = "returns a list of object"
  value       = data.azurerm_public_ips.this.public_ips
}

output "this" {
  value = azurerm_public_ips.this
}
```

[top](#index)