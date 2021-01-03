# azurerm_marketplace_agreement

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
module "azurerm_marketplace_agreement" {
  source = "./modules/azurerm/r/azurerm_marketplace_agreement"

  # offer - (required) is a type of string
  offer = null
  # plan - (required) is a type of string
  plan = null
  # publisher - (required) is a type of string
  publisher = null

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
variable "offer" {
  description = "(required)"
  type        = string
}

variable "plan" {
  description = "(required)"
  type        = string
}

variable "publisher" {
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
resource "azurerm_marketplace_agreement" "this" {
  offer     = var.offer
  plan      = var.plan
  publisher = var.publisher

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
  value       = azurerm_marketplace_agreement.this.id
}

output "license_text_link" {
  description = "returns a string"
  value       = azurerm_marketplace_agreement.this.license_text_link
}

output "privacy_policy_link" {
  description = "returns a string"
  value       = azurerm_marketplace_agreement.this.privacy_policy_link
}

output "this" {
  value = azurerm_marketplace_agreement.this
}
```

[top](#index)