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
    datadog = ">= 2.24.0"
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
  description = "(required) - The name attribute in the resource `datadog_logs_pipeline_order` needs to be unique. It's recommended to use the same value as the resource name. No related field is available in [Logs Pipeline API](https://docs.datadoghq.com/api/v1/logs-pipelines/#get-pipeline-order)."
  type        = string
}

variable "pipelines" {
  description = "(required) - The pipeline IDs list. The order of pipeline IDs in this attribute defines the overall pipeline order for logs."
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