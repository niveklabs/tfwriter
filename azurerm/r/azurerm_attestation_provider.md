# azurerm_attestation_provider

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
module "azurerm_attestation_provider" {
  source = "./modules/azurerm/r/azurerm_attestation_provider"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # policy_signing_certificate_data - (optional) is a type of string
  policy_signing_certificate_data = null
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
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_signing_certificate_data" {
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
resource "azurerm_attestation_provider" "this" {
  location                        = var.location
  name                            = var.name
  policy_signing_certificate_data = var.policy_signing_certificate_data
  resource_group_name             = var.resource_group_name
  tags                            = var.tags

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
output "attestation_uri" {
  description = "returns a string"
  value       = azurerm_attestation_provider.this.attestation_uri
}

output "id" {
  description = "returns a string"
  value       = azurerm_attestation_provider.this.id
}

output "trust_model" {
  description = "returns a string"
  value       = azurerm_attestation_provider.this.trust_model
}

output "this" {
  value = azurerm_attestation_provider.this
}
```

[top](#index)