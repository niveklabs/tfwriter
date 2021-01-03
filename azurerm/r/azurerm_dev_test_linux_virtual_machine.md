# azurerm_dev_test_linux_virtual_machine

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
module "azurerm_dev_test_linux_virtual_machine" {
  source = "./modules/azurerm/r/azurerm_dev_test_linux_virtual_machine"

  # allow_claim - (optional) is a type of bool
  allow_claim = null
  # disallow_public_ip_address - (optional) is a type of bool
  disallow_public_ip_address = null
  # lab_name - (required) is a type of string
  lab_name = null
  # lab_subnet_name - (required) is a type of string
  lab_subnet_name = null
  # lab_virtual_network_id - (required) is a type of string
  lab_virtual_network_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # notes - (optional) is a type of string
  notes = null
  # password - (optional) is a type of string
  password = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # size - (required) is a type of string
  size = null
  # ssh_key - (optional) is a type of string
  ssh_key = null
  # storage_type - (required) is a type of string
  storage_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # username - (required) is a type of string
  username = null

  gallery_image_reference = [{
    offer     = null
    publisher = null
    sku       = null
    version   = null
  }]

  inbound_nat_rule = [{
    backend_port  = null
    frontend_port = null
    protocol      = null
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
variable "allow_claim" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disallow_public_ip_address" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "lab_name" {
  description = "(required)"
  type        = string
}

variable "lab_subnet_name" {
  description = "(required)"
  type        = string
}

variable "lab_virtual_network_id" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = string
}

variable "ssh_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_type" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}

variable "gallery_image_reference" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      offer     = string
      publisher = string
      sku       = string
      version   = string
    }
  ))
}

variable "inbound_nat_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      backend_port  = number
      frontend_port = number
      protocol      = string
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
resource "azurerm_dev_test_linux_virtual_machine" "this" {
  allow_claim                = var.allow_claim
  disallow_public_ip_address = var.disallow_public_ip_address
  lab_name                   = var.lab_name
  lab_subnet_name            = var.lab_subnet_name
  lab_virtual_network_id     = var.lab_virtual_network_id
  location                   = var.location
  name                       = var.name
  notes                      = var.notes
  password                   = var.password
  resource_group_name        = var.resource_group_name
  size                       = var.size
  ssh_key                    = var.ssh_key
  storage_type               = var.storage_type
  tags                       = var.tags
  username                   = var.username

  dynamic "gallery_image_reference" {
    for_each = var.gallery_image_reference
    content {
      offer     = gallery_image_reference.value["offer"]
      publisher = gallery_image_reference.value["publisher"]
      sku       = gallery_image_reference.value["sku"]
      version   = gallery_image_reference.value["version"]
    }
  }

  dynamic "inbound_nat_rule" {
    for_each = var.inbound_nat_rule
    content {
      backend_port = inbound_nat_rule.value["backend_port"]
      protocol     = inbound_nat_rule.value["protocol"]
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
output "fqdn" {
  description = "returns a string"
  value       = azurerm_dev_test_linux_virtual_machine.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = azurerm_dev_test_linux_virtual_machine.this.id
}

output "unique_identifier" {
  description = "returns a string"
  value       = azurerm_dev_test_linux_virtual_machine.this.unique_identifier
}

output "this" {
  value = azurerm_dev_test_linux_virtual_machine.this
}
```

[top](#index)