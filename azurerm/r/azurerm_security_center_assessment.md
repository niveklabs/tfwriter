# azurerm_security_center_assessment

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
module "azurerm_security_center_assessment" {
  source = "./modules/azurerm/r/azurerm_security_center_assessment"

  # additional_data - (optional) is a type of map of string
  additional_data = {}
  # assessment_policy_id - (required) is a type of string
  assessment_policy_id = null
  # target_resource_id - (required) is a type of string
  target_resource_id = null

  status = [{
    cause       = null
    code        = null
    description = null
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
variable "additional_data" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "assessment_policy_id" {
  description = "(required)"
  type        = string
}

variable "target_resource_id" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cause       = string
      code        = string
      description = string
    }
  ))
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
resource "azurerm_security_center_assessment" "this" {
  additional_data      = var.additional_data
  assessment_policy_id = var.assessment_policy_id
  target_resource_id   = var.target_resource_id

  dynamic "status" {
    for_each = var.status
    content {
      cause       = status.value["cause"]
      code        = status.value["code"]
      description = status.value["description"]
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
  value       = azurerm_security_center_assessment.this.id
}

output "this" {
  value = azurerm_security_center_assessment.this
}
```

[top](#index)