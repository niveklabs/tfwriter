# azurerm_virtual_hub_ip

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
module "azurerm_virtual_hub_ip" {
  source = "./modules/azurerm/r/azurerm_virtual_hub_ip"

  # name - (required) is a type of string
  name = null
  # private_ip_address - (optional) is a type of string
  private_ip_address = null
  # private_ip_allocation_method - (optional) is a type of string
  private_ip_allocation_method = null
  # public_ip_address_id - (optional) is a type of string
  public_ip_address_id = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # virtual_hub_id - (required) is a type of string
  virtual_hub_id = null

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
variable "name" {
  description = "(required)"
  type        = string
}

variable "private_ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip_allocation_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_ip_address_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "virtual_hub_id" {
  description = "(required)"
  type        = string
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
resource "azurerm_virtual_hub_ip" "this" {
  # name - (required) is a type of string
  name = var.name
  # private_ip_address - (optional) is a type of string
  private_ip_address = var.private_ip_address
  # private_ip_allocation_method - (optional) is a type of string
  private_ip_allocation_method = var.private_ip_allocation_method
  # public_ip_address_id - (optional) is a type of string
  public_ip_address_id = var.public_ip_address_id
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id
  # virtual_hub_id - (required) is a type of string
  virtual_hub_id = var.virtual_hub_id

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
  value       = azurerm_virtual_hub_ip.this.id
}

output "this" {
  value = azurerm_virtual_hub_ip.this
}
```

[top](#index)