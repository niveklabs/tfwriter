# azurerm_spring_cloud_certificate

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
module "azurerm_spring_cloud_certificate" {
  source = "./modules/azurerm/r/azurerm_spring_cloud_certificate"

  # key_vault_certificate_id - (required) is a type of string
  key_vault_certificate_id = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_name - (required) is a type of string
  service_name = null

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
variable "key_vault_certificate_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "service_name" {
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
resource "azurerm_spring_cloud_certificate" "this" {
  key_vault_certificate_id = var.key_vault_certificate_id
  name                     = var.name
  resource_group_name      = var.resource_group_name
  service_name             = var.service_name

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
  value       = azurerm_spring_cloud_certificate.this.id
}

output "thumbprint" {
  description = "returns a string"
  value       = azurerm_spring_cloud_certificate.this.thumbprint
}

output "this" {
  value = azurerm_spring_cloud_certificate.this
}
```

[top](#index)