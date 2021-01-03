# datadog_logs_integration_pipeline

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
module "datadog_logs_integration_pipeline" {
  source = "./modules/datadog/r/datadog_logs_integration_pipeline"

  # is_enabled - (optional) is a type of bool
  is_enabled = null
}
```

[top](#index)

### Variables

```terraform
variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_logs_integration_pipeline" "this" {
  is_enabled = var.is_enabled
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_logs_integration_pipeline.this.id
}

output "this" {
  value = datadog_logs_integration_pipeline.this
}
```

[top](#index)