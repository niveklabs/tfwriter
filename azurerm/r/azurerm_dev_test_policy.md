# azurerm_dev_test_policy

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
module "azurerm_dev_test_policy" {
  source = "./modules/azurerm/r/azurerm_dev_test_policy"

  # description - (optional) is a type of string
  description = null
  # evaluator_type - (required) is a type of string
  evaluator_type = null
  # fact_data - (optional) is a type of string
  fact_data = null
  # lab_name - (required) is a type of string
  lab_name = null
  # name - (required) is a type of string
  name = null
  # policy_set_name - (required) is a type of string
  policy_set_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # threshold - (required) is a type of string
  threshold = null

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

variable "evaluator_type" {
  description = "(required)"
  type        = string
}

variable "fact_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lab_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_set_name" {
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

variable "threshold" {
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
resource "azurerm_dev_test_policy" "this" {
  description         = var.description
  evaluator_type      = var.evaluator_type
  fact_data           = var.fact_data
  lab_name            = var.lab_name
  name                = var.name
  policy_set_name     = var.policy_set_name
  resource_group_name = var.resource_group_name
  tags                = var.tags
  threshold           = var.threshold

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
  value       = azurerm_dev_test_policy.this.id
}

output "this" {
  value = azurerm_dev_test_policy.this
}
```

[top](#index)