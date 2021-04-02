# azurerm_network_interface_application_security_group_association

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
module "azurerm_network_interface_application_security_group_association" {
  source = "./modules/azurerm/r/azurerm_network_interface_application_security_group_association"

  # application_security_group_id - (required) is a type of string
  application_security_group_id = null
  # network_interface_id - (required) is a type of string
  network_interface_id = null

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
variable "application_security_group_id" {
  description = "(required)"
  type        = string
}

variable "network_interface_id" {
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
resource "azurerm_network_interface_application_security_group_association" "this" {
  application_security_group_id = var.application_security_group_id
  network_interface_id          = var.network_interface_id

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
  value       = azurerm_network_interface_application_security_group_association.this.id
}

output "this" {
  value = azurerm_network_interface_application_security_group_association.this
}
```

[top](#index)