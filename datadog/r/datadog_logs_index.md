# datadog_logs_index

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
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_logs_index" {
  source = "./modules/datadog/r/datadog_logs_index"

  # name - (required) is a type of string
  name = null

  exclusion_filter = [{
    filter = [{
      query       = null
      sample_rate = null
    }]
    is_enabled = null
    name       = null
  }]

  filter = [{
    query = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "exclusion_filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      filter = list(object(
        {
          query       = string
          sample_rate = number
        }
      ))
      is_enabled = bool
      name       = string
    }
  ))
  default = []
}

variable "filter" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      query = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "datadog_logs_index" "this" {
  name = var.name

  dynamic "exclusion_filter" {
    for_each = var.exclusion_filter
    content {
      is_enabled = exclusion_filter.value["is_enabled"]
      name       = exclusion_filter.value["name"]

      dynamic "filter" {
        for_each = exclusion_filter.value.filter
        content {
          query       = filter.value["query"]
          sample_rate = filter.value["sample_rate"]
        }
      }

    }
  }

  dynamic "filter" {
    for_each = var.filter
    content {
      query = filter.value["query"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_logs_index.this.id
}

output "this" {
  value = datadog_logs_index.this
}
```

[top](#index)