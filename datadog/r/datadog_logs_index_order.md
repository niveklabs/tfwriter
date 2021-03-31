# datadog_logs_index_order

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
module "datadog_logs_index_order" {
  source = "./modules/datadog/r/datadog_logs_index_order"

  # indexes - (required) is a type of list of string
  indexes = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "indexes" {
  description = "(required) - The index resource list. Logs are tested against the query filter of each index one by one following the order of the list."
  type        = list(string)
}

variable "name" {
  description = "(required) - The unique name of the index order resource."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "datadog_logs_index_order" "this" {
  indexes = var.indexes
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_logs_index_order.this.id
}

output "this" {
  value = datadog_logs_index_order.this
}
```

[top](#index)