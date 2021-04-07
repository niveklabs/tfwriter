# datadog_slo_correction

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
module "datadog_slo_correction" {
  source = "./modules/datadog/r/datadog_slo_correction"

  # category - (required) is a type of string
  category = null
  # description - (optional) is a type of string
  description = null
  # end - (required) is a type of number
  end = null
  # slo_id - (required) is a type of string
  slo_id = null
  # start - (required) is a type of number
  start = null
  # timezone - (optional) is a type of string
  timezone = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(required) - Category the SLO correction belongs to"
  type        = string
}

variable "description" {
  description = "(optional) - Description of the correction being made."
  type        = string
  default     = null
}

variable "end" {
  description = "(required) - Ending time of the correction in epoch seconds"
  type        = number
}

variable "slo_id" {
  description = "(required) - ID of the SLO that this correction will be applied to"
  type        = string
}

variable "start" {
  description = "(required) - Starting time of the correction in epoch seconds"
  type        = number
}

variable "timezone" {
  description = "(optional) - The timezone to display in the UI for the correction times (defaults to \"UTC\")"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_slo_correction" "this" {
  # category - (required) is a type of string
  category = var.category
  # description - (optional) is a type of string
  description = var.description
  # end - (required) is a type of number
  end = var.end
  # slo_id - (required) is a type of string
  slo_id = var.slo_id
  # start - (required) is a type of number
  start = var.start
  # timezone - (optional) is a type of string
  timezone = var.timezone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_slo_correction.this.id
}

output "this" {
  value = datadog_slo_correction.this
}
```

[top](#index)