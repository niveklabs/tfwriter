# azurerm_app_service_certificate

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_app_service_certificate" {
  source = "./modules/azurerm/d/azurerm_app_service_certificate"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
data "azurerm_app_service_certificate" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "expiration_date" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate.this.expiration_date
}

output "friendly_name" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate.this.friendly_name
}

output "host_names" {
  description = "returns a list of string"
  value       = data.azurerm_app_service_certificate.this.host_names
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate.this.id
}

output "issue_date" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate.this.issue_date
}

output "issuer" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate.this.issuer
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate.this.location
}

output "subject_name" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate.this.subject_name
}

output "thumbprint" {
  description = "returns a string"
  value       = data.azurerm_app_service_certificate.this.thumbprint
}

output "this" {
  value = azurerm_app_service_certificate.this
}
```

[top](#index)