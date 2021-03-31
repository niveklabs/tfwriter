# azurerm_policy_set_definition

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
module "azurerm_policy_set_definition" {
  source = "./modules/azurerm/r/azurerm_policy_set_definition"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # management_group_id - (optional) is a type of string
  management_group_id = null
  # management_group_name - (optional) is a type of string
  management_group_name = null
  # metadata - (optional) is a type of string
  metadata = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of string
  parameters = null
  # policy_definitions - (optional) is a type of string
  policy_definitions = null
  # policy_type - (required) is a type of string
  policy_type = null

  policy_definition_group = [{
    additional_metadata_resource_id = null
    category                        = null
    description                     = null
    display_name                    = null
    name                            = null
  }]

  policy_definition_reference = [{
    parameter_values     = null
    parameters           = {}
    policy_definition_id = null
    policy_group_names   = []
    reference_id         = null
  }]

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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "management_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "management_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_definitions" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_type" {
  description = "(required)"
  type        = string
}

variable "policy_definition_group" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      additional_metadata_resource_id = string
      category                        = string
      description                     = string
      display_name                    = string
      name                            = string
    }
  ))
  default = []
}

variable "policy_definition_reference" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      parameter_values     = string
      parameters           = map(string)
      policy_definition_id = string
      policy_group_names   = set(string)
      reference_id         = string
    }
  ))
  default = []
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
resource "azurerm_policy_set_definition" "this" {
  description           = var.description
  display_name          = var.display_name
  management_group_id   = var.management_group_id
  management_group_name = var.management_group_name
  metadata              = var.metadata
  name                  = var.name
  parameters            = var.parameters
  policy_definitions    = var.policy_definitions
  policy_type           = var.policy_type

  dynamic "policy_definition_group" {
    for_each = var.policy_definition_group
    content {
      additional_metadata_resource_id = policy_definition_group.value["additional_metadata_resource_id"]
      category                        = policy_definition_group.value["category"]
      description                     = policy_definition_group.value["description"]
      display_name                    = policy_definition_group.value["display_name"]
      name                            = policy_definition_group.value["name"]
    }
  }

  dynamic "policy_definition_reference" {
    for_each = var.policy_definition_reference
    content {
      parameter_values     = policy_definition_reference.value["parameter_values"]
      parameters           = policy_definition_reference.value["parameters"]
      policy_definition_id = policy_definition_reference.value["policy_definition_id"]
      policy_group_names   = policy_definition_reference.value["policy_group_names"]
      reference_id         = policy_definition_reference.value["reference_id"]
    }
  }

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
  value       = azurerm_policy_set_definition.this.id
}

output "management_group_id" {
  description = "returns a string"
  value       = azurerm_policy_set_definition.this.management_group_id
}

output "management_group_name" {
  description = "returns a string"
  value       = azurerm_policy_set_definition.this.management_group_name
}

output "metadata" {
  description = "returns a string"
  value       = azurerm_policy_set_definition.this.metadata
}

output "policy_definitions" {
  description = "returns a string"
  value       = azurerm_policy_set_definition.this.policy_definitions
}

output "this" {
  value = azurerm_policy_set_definition.this
}
```

[top](#index)