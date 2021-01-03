# azurerm_nat_gateway_public_ip_association

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
module "azurerm_nat_gateway_public_ip_association" {
  source = "./modules/azurerm/r/azurerm_nat_gateway_public_ip_association"

  # nat_gateway_id - (required) is a type of string
  nat_gateway_id = null
  # public_ip_address_id - (required) is a type of string
  public_ip_address_id = null

  timeouts = [{
    create = null
    delete = null
    read   = null
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

variable "public_ip_address_id" {
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_nat_gateway_public_ip_association" "this" {
  nat_gateway_id       = var.nat_gateway_id
  public_ip_address_id = var.public_ip_address_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_nat_gateway_public_ip_association.this.id
}

output "this" {
  value = azurerm_nat_gateway_public_ip_association.this
}
```

[top](#index)