# datadog_logs_metric

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
module "datadog_logs_metric" {
  source = "./modules/datadog/r/datadog_logs_metric"

  # name - (required) is a type of string
  name = null

  compute = [{
    aggregation_type = null
    path             = null
  }]

  filter = [{
    query = null
  }]

  group_by = [{
    path     = null
    tag_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the log-based metric. This field can't be updated after creation."
  type        = string
}

variable "compute" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      aggregation_type = string
      path             = string
    }
  ))
}

variable "filter" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      query = string
    }
  ))
}

variable "group_by" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      path     = string
      tag_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_logs_metric" "this" {
  name = var.name

  dynamic "compute" {
    for_each = var.compute
    content {
      aggregation_type = compute.value["aggregation_type"]
      path             = compute.value["path"]
    }
  }

  dynamic "filter" {
    for_each = var.filter
    content {
      query = filter.value["query"]
    }
  }

  dynamic "group_by" {
    for_each = var.group_by
    content {
      path     = group_by.value["path"]
      tag_name = group_by.value["tag_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_logs_metric.this.id
}

output "this" {
  value = datadog_logs_metric.this
}
```

[top](#index)