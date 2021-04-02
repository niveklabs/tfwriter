# azurerm_app_service_certificate_order

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
module "azurerm_app_service_certificate_order" {
  source = "./modules/azurerm/r/azurerm_app_service_certificate_order"

  # auto_renew - (optional) is a type of bool
  auto_renew = null
  # csr - (optional) is a type of string
  csr = null
  # distinguished_name - (optional) is a type of string
  distinguished_name = null
  # key_size - (optional) is a type of number
  key_size = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # product_type - (optional) is a type of string
  product_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # validity_in_years - (optional) is a type of number
  validity_in_years = null

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
variable "auto_renew" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "csr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distinguished_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "product_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "validity_in_years" {
  description = "(optional)"
  type        = number
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
resource "azurerm_app_service_certificate_order" "this" {
  auto_renew          = var.auto_renew
  csr                 = var.csr
  distinguished_name  = var.distinguished_name
  key_size            = var.key_size
  location            = var.location
  name                = var.name
  product_type        = var.product_type
  resource_group_name = var.resource_group_name
  tags                = var.tags
  validity_in_years   = var.validity_in_years

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
output "app_service_certificate_not_renewable_reasons" {
  description = "returns a list of string"
  value       = azurerm_app_service_certificate_order.this.app_service_certificate_not_renewable_reasons
}

output "certificates" {
  description = "returns a list of object"
  value       = azurerm_app_service_certificate_order.this.certificates
}

output "csr" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_order.this.csr
}

output "distinguished_name" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_order.this.distinguished_name
}

output "domain_verification_token" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_order.this.domain_verification_token
}

output "expiration_time" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_order.this.expiration_time
}

output "id" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_order.this.id
}

output "intermediate_thumbprint" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_order.this.intermediate_thumbprint
}

output "is_private_key_external" {
  description = "returns a bool"
  value       = azurerm_app_service_certificate_order.this.is_private_key_external
}

output "root_thumbprint" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_order.this.root_thumbprint
}

output "signed_certificate_thumbprint" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_order.this.signed_certificate_thumbprint
}

output "status" {
  description = "returns a string"
  value       = azurerm_app_service_certificate_order.this.status
}

output "this" {
  value = azurerm_app_service_certificate_order.this
}
```

[top](#index)