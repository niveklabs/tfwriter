# azurerm_subnet_nat_gateway_association

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
module "azurerm_subnet_nat_gateway_association" {
  source = "./modules/azurerm/r/azurerm_subnet_nat_gateway_association"

  # nat_gateway_id - (required) is a type of string
  nat_gateway_id = null
  # subnet_id - (required) is a type of string
  subnet_id = null

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
variable "nat_gateway_id" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
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
resource "azurerm_subnet_nat_gateway_association" "this" {
  nat_gateway_id = var.nat_gateway_id
  subnet_id      = var.subnet_id

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
  value       = azurerm_subnet_nat_gateway_association.this.id
}

output "this" {
  value = azurerm_subnet_nat_gateway_association.this
}
```

[top](#index)