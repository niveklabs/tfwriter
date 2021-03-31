# datadog_dashboard_list

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_dashboard_list" {
  source = "./modules/datadog/r/datadog_dashboard_list"

  # name - (required) is a type of string
  name = null

  dash_item = [{
    dash_id = null
    type    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the Dashboard List"
  type        = string
}

variable "dash_item" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dash_id = string
      type    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_dashboard_list" "this" {
  name = var.name

  dynamic "dash_item" {
    for_each = var.dash_item
    content {
      dash_id = dash_item.value["dash_id"]
      type    = dash_item.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_dashboard_list.this.id
}

output "this" {
  value = datadog_dashboard_list.this
}
```

[top](#index)