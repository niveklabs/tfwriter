# azurerm_policy_remediation

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
module "azurerm_policy_remediation" {
  source = "./modules/azurerm/r/azurerm_policy_remediation"

  # location_filters - (optional) is a type of list of string
  location_filters = []
  # name - (required) is a type of string
  name = null
  # policy_assignment_id - (required) is a type of string
  policy_assignment_id = null
  # policy_definition_reference_id - (optional) is a type of string
  policy_definition_reference_id = null
  # resource_discovery_mode - (optional) is a type of string
  resource_discovery_mode = null
  # scope - (required) is a type of string
  scope = null

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
variable "location_filters" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_assignment_id" {
  description = "(required)"
  type        = string
}

variable "policy_definition_reference_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_discovery_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
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
resource "azurerm_policy_remediation" "this" {
  location_filters               = var.location_filters
  name                           = var.name
  policy_assignment_id           = var.policy_assignment_id
  policy_definition_reference_id = var.policy_definition_reference_id
  resource_discovery_mode        = var.resource_discovery_mode
  scope                          = var.scope

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
  value       = azurerm_policy_remediation.this.id
}

output "this" {
  value = azurerm_policy_remediation.this
}
```

[top](#index)