# azurerm_app_service_certificate_order

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/azurerm/d/azurerm_app_service_certificate_order"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_app_service_certificate_order" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "app_service_certificate_not_renewable_reasons" {
  description = "returns a list of string"
  value       = data.azurerm_app_service_certificate_order.this.app_service_certificate_not_renewable_reasons
}

output "auto_renew" {
  description = "returns a bool"
  value       = data.azurerm_app_service_certificate_order.this.auto_renew
}

output "certificates" {
  description = "returns a list of object"
  value       = data.azurerm_app_service_certificate_order.this.certificates
}

output "csr" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.csr
}

output "distinguished_name" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.distinguished_name
}

output "domain_verification_token" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.domain_verification_token
}

output "expiration_time" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.expiration_time
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.id
}

output "intermediate_thumbprint" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.intermediate_thumbprint
}

output "is_private_key_external" {
  description = "returns a bool"
  value       = data.azurerm_app_service_certificate_order.this.is_private_key_external
}

output "key_size" {
  description = "returns a number"
  value       = data.azurerm_app_service_certificate_order.this.key_size
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.location
}

output "product_type" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.product_type
}

output "root_thumbprint" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.root_thumbprint
}

output "signed_certificate_thumbprint" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.signed_certificate_thumbprint
}

output "status" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate_order.this.status
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_app_service_certificate_order.this.tags
}

output "validity_in_years" {
  description = "returns a number"
  value       = data.azurerm_app_service_certificate_order.this.validity_in_years
}

output "this" {
  value = azurerm_app_service_certificate_order.this
}
```

[top](#index)