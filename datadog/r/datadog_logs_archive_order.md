# datadog_logs_archive_order

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
module "datadog_logs_archive_order" {
  source = "./modules/datadog/r/datadog_logs_archive_order"

  # archive_ids - (optional) is a type of list of string
  archive_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "archive_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_logs_archive_order" "this" {
  archive_ids = var.archive_ids
}
```

[top](#index)

### Outputs

```terraform
output "archive_ids" {
  description = "returns a list of string"
  value       = datadog_logs_archive_order.this.archive_ids
}

output "id" {
  description = "returns a string"
  value       = datadog_logs_archive_order.this.id
}

output "this" {
  value = datadog_logs_archive_order.this
}
```

[top](#index)