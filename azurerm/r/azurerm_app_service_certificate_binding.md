# azurerm_app_service_certificate_binding

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
module "azurerm_app_service_certificate_binding" {
  source = "./modules/azurerm/r/azurerm_app_service_certificate_binding"

  # certificate_id - (required) is a type of string
  certificate_id = null
  # hostname_binding_id - (required) is a type of string
  hostname_binding_id = null
  # ssl_state - (required) is a type of string
  ssl_state = null

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
variable "certificate_id" {
  description = "(required)"
  type        = string
}

variable "hostname_binding_id" {
  description = "(required)"
  type        = string
}

variable "ssl_state" {
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
resource "azurerm_app_service_certificate_binding" "this" {
  certificate_id      = var.certificate_id
  hostname_binding_id = var.hostname_binding_id
  ssl_state           = var.ssl_state

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
output "app_service_name" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_binding.this.app_service_name
}

output "hostname" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_binding.this.hostname
}

output "id" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_binding.this.id
}

output "thumbprint" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_binding.this.thumbprint
}

output "this" {
  value = azurerm_app_service_certificate_binding.this
}
```

[top](#index)