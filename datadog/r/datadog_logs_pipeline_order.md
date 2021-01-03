# datadog_logs_pipeline_order

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
module "datadog_logs_pipeline_order" {
  source = "./modules/datadog/r/datadog_logs_pipeline_order"

  # name - (required) is a type of string
  name = null
  # pipelines - (required) is a type of list of string
  pipelines = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "pipelines" {
  description = "(required)"
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "datadog_logs_pipeline_order" "this" {
  name      = var.name
  pipelines = var.pipelines
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_logs_pipeline_order.this.id
}

output "this" {
  value = datadog_logs_pipeline_order.this
}
```

[top](#index)