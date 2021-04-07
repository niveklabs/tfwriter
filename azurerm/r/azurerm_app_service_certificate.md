# azurerm_app_service_certificate

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
module "azurerm_app_service_certificate" {
  source = "./modules/azurerm/r/azurerm_app_service_certificate"

  # hosting_environment_profile_id - (optional) is a type of string
  hosting_environment_profile_id = null
  # key_vault_secret_id - (optional) is a type of string
  key_vault_secret_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # pfx_blob - (optional) is a type of string
  pfx_blob = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
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
variable "hosting_environment_profile_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_vault_secret_id" {
  description = "(optional)"
  type        = string
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

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pfx_blob" {
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
resource "azurerm_app_service_certificate" "this" {
  # hosting_environment_profile_id - (optional) is a type of string
  hosting_environment_profile_id = var.hosting_environment_profile_id
  # key_vault_secret_id - (optional) is a type of string
  key_vault_secret_id = var.key_vault_secret_id
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # pfx_blob - (optional) is a type of string
  pfx_blob = var.pfx_blob
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "expiration_date" {
  description = "returns a string"
  value       = azurerm_app_service_certificate.this.expiration_date
}

output "friendly_name" {
  description = "returns a string"
  value       = azurerm_app_service_certificate.this.friendly_name
}

output "host_names" {
  description = "returns a list of string"
  value       = azurerm_app_service_certificate.this.host_names
}

output "id" {
  description = "returns a string"
  value       = azurerm_app_service_certificate.this.id
}

output "issue_date" {
  description = "returns a string"
  value       = azurerm_app_service_certificate.this.issue_date
}

output "issuer" {
  description = "returns a string"
  value       = azurerm_app_service_certificate.this.issuer
}

output "subject_name" {
  description = "returns a string"
  value       = azurerm_app_service_certificate.this.subject_name
}

output "thumbprint" {
  description = "returns a string"
  value       = azurerm_app_service_certificate.this.thumbprint
}

output "this" {
  value = azurerm_app_service_certificate.this
}
```

[top](#index)