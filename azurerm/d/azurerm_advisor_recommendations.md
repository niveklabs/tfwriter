# azurerm_advisor_recommendations

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
module "azurerm_advisor_recommendations" {
  source = "./modules/azurerm/d/azurerm_advisor_recommendations"

  # filter_by_category - (optional) is a type of set of string
  filter_by_category = []
  # filter_by_resource_groups - (optional) is a type of set of string
  filter_by_resource_groups = []

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter_by_category" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "filter_by_resource_groups" {
  description = "(optional)"
  type        = set(string)
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
data "azurerm_advisor_recommendations" "this" {
  filter_by_category        = var.filter_by_category
  filter_by_resource_groups = var.filter_by_resource_groups

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_advisor_recommendations.this.id
}

output "recommendations" {
  description = "returns a list of object"
  value       = data.azurerm_advisor_recommendations.this.recommendations
}

output "this" {
  value = azurerm_advisor_recommendations.this
}
```

[top](#index)