# azurerm_app_service_managed_certificate

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
module "azurerm_app_service_managed_certificate" {
  source = "./modules/azurerm/r/azurerm_app_service_managed_certificate"

  # custom_hostname_binding_id - (required) is a type of string
  custom_hostname_binding_id = null
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
variable "custom_hostname_binding_id" {
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
resource "azurerm_app_service_managed_certificate" "this" {
  custom_hostname_binding_id = var.custom_hostname_binding_id
  tags                       = var.tags

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
output "canonical_name" {
  description = "returns a string"
  value       = azurerm_app_service_managed_certificate.this.canonical_name
}

output "expiration_date" {
  description = "returns a string"
  value       = azurerm_app_service_managed_certificate.this.expiration_date
}

output "friendly_name" {
  description = "returns a string"
  value       = azurerm_app_service_managed_certificate.this.friendly_name
}

output "host_names" {
  description = "returns a list of string"
  value       = azurerm_app_service_managed_certificate.this.host_names
}

output "id" {
  description = "returns a string"
  value       = azurerm_app_service_managed_certificate.this.id
}

output "issue_date" {
  description = "returns a string"
  value       = azurerm_app_service_managed_certificate.this.issue_date
}

output "issuer" {
  description = "returns a string"
  value       = azurerm_app_service_managed_certificate.this.issuer
}

output "subject_name" {
  description = "returns a string"
  value       = azurerm_app_service_managed_certificate.this.subject_name
}

output "thumbprint" {
  description = "returns a string"
  value       = azurerm_app_service_managed_certificate.this.thumbprint
}

output "this" {
  value = azurerm_app_service_managed_certificate.this
}
```

[top](#index)