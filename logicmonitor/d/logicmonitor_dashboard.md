# logicmonitor_dashboard

[back](../logicmonitor.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    logicmonitor = ">= 1.3.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "logicmonitor_dashboard" {
  source = "./modules/logicmonitor/d/logicmonitor_dashboard"

  # offset - (optional) is a type of number
  offset = null
  # size - (optional) is a type of number
  size = null

  filters = [{
    custom_property_name  = null
    custom_property_value = null
    operator              = null
    property              = null
    value                 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "offset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "filters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      custom_property_name  = string
      custom_property_value = string
      operator              = string
      property              = string
      value                 = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "logicmonitor_dashboard" "this" {
  offset = var.offset
  size   = var.size

  dynamic "filters" {
    for_each = var.filters
    content {
      custom_property_name  = filters.value["custom_property_name"]
      custom_property_value = filters.value["custom_property_value"]
      operator              = filters.value["operator"]
      property              = filters.value["property"]
      value                 = filters.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.logicmonitor_dashboard.this.id
}

output "this" {
  value = logicmonitor_dashboard.this
}
```

[top](#index)