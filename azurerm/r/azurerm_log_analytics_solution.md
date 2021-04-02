# azurerm_log_analytics_solution

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
module "azurerm_log_analytics_solution" {
  source = "./modules/azurerm/r/azurerm_log_analytics_solution"

  # location - (required) is a type of string
  location = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # solution_name - (required) is a type of string
  solution_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # workspace_name - (required) is a type of string
  workspace_name = null
  # workspace_resource_id - (required) is a type of string
  workspace_resource_id = null

  plan = [{
    name           = null
    product        = null
    promotion_code = null
    publisher      = null
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
variable "location" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "solution_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "workspace_name" {
  description = "(required)"
  type        = string
}

variable "workspace_resource_id" {
  description = "(required)"
  type        = string
}

variable "plan" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      name           = string
      product        = string
      promotion_code = string
      publisher      = string
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
resource "azurerm_log_analytics_solution" "this" {
  location              = var.location
  resource_group_name   = var.resource_group_name
  solution_name         = var.solution_name
  tags                  = var.tags
  workspace_name        = var.workspace_name
  workspace_resource_id = var.workspace_resource_id

  dynamic "plan" {
    for_each = var.plan
    content {
      product        = plan.value["product"]
      promotion_code = plan.value["promotion_code"]
      publisher      = plan.value["publisher"]
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
  value       = azurerm_log_analytics_solution.this.id
}

output "this" {
  value = azurerm_log_analytics_solution.this
}
```

[top](#index)